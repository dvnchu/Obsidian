
# Core Concepts
## CIA Triad
* *Confidentiality*
	Prevent disclosure of information to unauthorized individuals or systems
	 - Encryption
	 - Access controls
	 - 2FA
* *Integrity*
	 Data is stored and transferred as intended
	- Hashing
	- Certificates
	- [[Fundamental Security Concepts#Non-repudiation|Non repudiation]]
* *Availability*
	Info is accessible to authorized users
	- Redundancy
	- Fault tolerance
	- Patching
## Non-repudiation
You cant deny what you've said
- Proof of integrity (hashes)
- proof of origin
## AAA framework
Identification: who you claim to be, usually username
Authentication: Prove you are who you say you are
Authorization: What access do you have
Accounting: logging, time data login and out

**System auths**
- you manage many devices, and sometimes cant use a password.
- digitally signed cert on the device verified by vpn concentrator or management software
	 Org has **Certificate authority(CA)**
- apply an authorization model
- define roles for permissions 

adds abstraction and makes easier to understand authorizations!
# Zero trust
*cover every device process person everything must be verified, nothing is trusted inherently*

Split the network into functional planes
- Data plane
	Process frames packets and network data
	processing forwarding trunking encrypting NAT
- Control plane
	Manages the actions of the data plane
	define policies and rules
	determines how packets are forwarded
	routing tables,  session tables, nat tables

hardware and software can be separated in this planes

**Policy enforcement point**
Its kind of a gatekeeper all traffic must pass trough here to enter our enterprise.
allows monitor and terminate connections.
can be thought as a various devices trying to identify an untrusted visitor.

Policy decision point: theres a process for making an auth decision
policy engine: evaluates each access decision based on policy and other information sources
Policy administrator: communicates with PEP
generates tokens or credentials
tells PEP to allow or disallow access
![[Pasted image 20260411200930.png]]

You can be trusted or entrusted depending on things like:
VPN
internal or external network
area


# Gap analysis
Where you are vs where you want to be

"frameworks"
depends on end goal
NIST special publication 800-171
ISO/IEC 27001
information security management systems
*analysis*
	Comparison
	Identify weaknesses
	examine broad security categories and break down them into smaller segments

# Physical security

Barricades/Bollards
channel people, avoid cars and trucks

Access control vestibules
Filter door access at same times manage people control

Fencing

Video surveillance

Guards and access badges

Lighting
More light is more security

Sensors
infrared pressure microwave ultrasonic

# Deception and disruption

Honeypots
Pretty useful to recon what the attackers are trying to do 

Honeynets
a larger deception network with one or more honypots you can use router servers firewalls

Honeyfiles
File with fake info, it can send an alert

Honeytokens
Track the malicious actors add traceable data to the honeynet
like API credentials, fake email addresses
database records browser cookies pixels etc
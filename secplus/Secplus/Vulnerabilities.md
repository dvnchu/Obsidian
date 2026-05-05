## Memory injections
Malware runs in memory
Malware can run as its own process or insert inself in the middle of an existing process

Injection  allows  malware to have the same rights than the occupied process

**DLL injection**
The attacker injects a path to a malicious DLL as part of a process

# Buffer overflow attack
Overwriting buffer of memory

# Race condition
Two events happen at nearly the same time, app doesnt account this
TOCTOU (Time of check to time of use attack)

# Malicious updates
Updates often include bug fixes and security patches; Maintain up to date
Always have a backup
install from trusted sources
Automated updates are relatively trustworthy (there are cases where the update had malicious code SolarWinds Orion)


# Operating Systems
Very complex code open for security issues

# SQL injection
Attacker puts request into the app works if app doesnt have proper checks
`SELECT * FROM users WHERE name = 'Professor' OR '1' = '1'`
Pulls all users as 1 always equal 1


# Cross-Site Scripting (XSS)
*Info from one site could be shared with another*

Non Persistent (reflected) attack
Web allows scripts to run in user innput
scripta sends credentials/sesison ids/cookies to the attacker
Script embedded in URL executes in victim browser

Persistent (stored)
Post it in social network now its "persistent"
it can spread really quickly

# Hardware
Everything is connecting to the network (IoT everywhere)
These devices are a potential security issues
Vendors can fix issues but dont always care

They sometimes have End of Life (EOL)
	it may still have patches and support
then End of Service life (EOSL)
stops selling product and no longer supported or available


# Virtualization security
 - Local privilege escalations
 - command injection
 - information disclosure
 
 **VM escape**
 Break out of the vm and move to other VM on the same hypervisor

Resources can be reused between VMs
Data can be inadvertently be shared between VMs


# Cloud security
76% of orgs arent using MFA
63% of code in prod is unpatched

* Attack service
	DoS
	Auth bypass
	Directory traversal (faulty configs)
- attack the application
	XSS
	out of bounds write
	sql injection

# Supply chain risk
Raw materials, suppliers, manufacturers, distributors, costumers, consumer
attackers can infect any step along the way

Cant always control a service provider
consider ongoing security audits

# Misconfiguration
- Open permissions
- Unsecured admin accounts
- insecure protocols
	some arent encrypted
	Telnet, FTP, SMTP, IMAP
- default settings
- open ports and services (manageable with firewall)

# Mobile device security
Challenging to secure
packed with sensitive data and moving
constantly connected to the internet

you dont have access to OS
jailbreak/root

sideloading
you can sideload malicious apps
you circumvent security your MDM(Mobile device management) becomes relatively useless


# Zero day
Vulnerabilities not found yet

attackers keep these to themselves to create exploits

zero day attacks
an attack without a patch or method of mitigation
race to exploit the vulnerability vs create a patch
http://cve.mitre.org
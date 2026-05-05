# Port security
**EAP**
Extensible authentication protocol
Auth framework
based RFC standardgs
integrates with 802.1x AKA network access control (NAC)
- You dont access to the network until you auth

Used in conjunction with an authentication database (Radius, LDAP, TACACS+, Kerberos)


# Firewalls
*Universal security control*
Control the flow of network traffic
outbound and inbound data
inapprotpiate content
protection against evil


traditional works on layer 4 (based on port)
new gen works on layer 7 (based on app)

Encrypt traffic

most fw can be layer 3 devices routers

UTM unified threat management  (all in one)
- URL filter
- Malware inspection
- Spam filter
- CSU/DSU 
- routing and switching
- firewall
- IDS/IPS
- Bandwith shaper
- VPN endpoint/concentrator
only operate at level 4
all function cause performances drops

Next-generation firewall (NGFW)
OSI application layer
other names:
Application layer gateway
stateful multilayer inspection
deep packet inspection
every packet must be analyzed and categorized before a decision

Network-based firewalls
controls traffic flows based on the app

Intrusion prevention system
identify app 
vulnerability signatures to the traffic
Content filtering (url filtering content censor)

WAF (web application firewall)
applies rules to HTTP/HTTPS
allow or deny based on expected input
stops SQLi
focus of payment card security data security standard


# Secure communication
VPN 
encrypted data traversing a public network

Concentrator
Encryption/decryption access device 
often in firewalls

Encrypted tunnel
encrypt data
add new headers and trailers

SSL/TLS VPN (Secure sockets layer)
uses common SSL/TLS protocol (TCP/443)
no big VPN clients

authenticate users
No certificates or shared passwords
Can be run from a browser or usually light vpn client
On demand access from a remote device it connects vo a vpn concentrator

Site-to-site IPsec VPN
always-on
firewalls often act as VPN concentrators
have firewalls already in place

SD-WAN
software defined netowrking in a wide area network
Wan for the cloud
data centers used to be in one place
With cloud there isnt that need no more
theres still a data center but with sd wan you can connect directly to cloud


Secure Access Service Edge (SASE)
Update secure access for cloud services
a next gen VPN
security tech are in the cloud
SASE clients on all devices
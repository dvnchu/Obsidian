various ways to specify targets
IP range using -: 192.168.0.1-10
IP subnet /: 192.168.0.1/24
Hostname: specify a hostname

you should run nmap as root or using sudo

you can scan a local netowrk as in a nw you are connected to

and you can scan remote networks (at least one router separates our system from the network)

unlike local you cannot send and ARP request to the network


you can also discover the network services listening on the live hosts

an easy way to do this on a TCP port is to attempt to telnet to the port. Try to stablish connection with every target port
making the TPC three-way handshake with every target port
nmap connect scan is similar

-St connect scan
tries to complete TCP three-way handhsake with every target TCP port. if port is open and NMAP connects, Nmap will tear down the established connection

[[Redes]]
Virtual Private Network

Allows devices on separate networks to communicate securely by creating a dedicated path between each other over the internet(tunnel). Devices connected within this tunnel form their own private network

![[Pasted image 20251218160003.png]]
Devices on network #3 ares a part of network #1 and #2 but also form a private network #3 where only they can communicate over.

## VPN technology

### PPP
Tech used by PPTP allows for authentication and provide encryption of data. VPNs work by using a private key and a public certificate. And it must match for you to connect.
This tech is not capable of leaving a network by itself (non-routable)

### PPTP
Point-to-Point Tunneling Protocol; It allows the data from PPP to travel and leave a network.
Very easy to setup and supported. however it is weakly encripted.

### IPSec 
Internet Protocol Security; encrypts data using the IP framework
difficult to set up bue it boasts strong encryption also supported.
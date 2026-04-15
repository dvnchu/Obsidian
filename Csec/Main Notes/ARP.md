[[Redes]]

Address Resolution Protocol, allows a device to associate its MAC with an IP on the network
Each device on a network will keep a log of the MAC addresses associated with other devices(cache).
When devices wish to communicate with another, they will send a broadcast to the entire network searching for the specific device
2 types of messages:
**ARP request**
A message is broadcasted on the network, "What is the mac address that owns this IP" if  a device owns that IP they will send an 
**ARP reply** with its MAC address. The requesting device now can remember this mapping and store it in *ARP cache*.
![[Pasted image 20251218142041.png]]
[[Redes]]
designed to aggregate multiple devices with Ethernet.

More efficient than hubs/repeaters, they keep track of what device is connected to which port, when they receive a packet they know where to send it, reducing network traffic.
switches and routers can be connected to one another increasing the redundancy of a network by adding multiple paths for data to take.

Switches can operate at both [[OSI Model#2.Data Link|layer 2]] and [[OSI Model#3.Network|layer 3]] of the OSI model. However, these are exclusive in the sense that Layer 2 switches cannot operate at layer 3.

![[Pasted image 20251218154856.png]]
Layer 2 switches will forward [[Packets & Frames|frames]] onto the connected devices using their MAC.

Now, let's move onto layer 3 switches. These switches are more sophisticated than layer 2, as they can perform _some_ of the responsibilities of a router. Namely, these switches will send [[Packets & Frames|frames]] to devices (as layer 2 does) and route packets to other devices using the IP protocol.

### VLAN
Allows specific devices within a network to be virtually split up. This split means they can all benefit from things such as an Internet connection but are treated separately. This network separation provides security because it means that rules in place determine how specific devices communicate with each other.
![[Pasted image 20251218155118.png]]

Both areas will have access to internet but they cant communicate with each other.
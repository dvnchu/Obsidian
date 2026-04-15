tags: [[Redes]]

Open Systems Interconnection Model
it dictates how all networked devices will send, receive and interpret data.
![[Pasted image 20251217173909.png]]

## 1.Physical Layer
Hardware used in networking, Devices use electrical signal to transfer data between each other in binary.

## 2.Data Link
Focuses on the physical addressing of the transmission.
it receives a package from the network layer and adds in the MAC address of the receiving endpoint.
inside every network enabled computer is a network interface card (NIC) which comes with a unique MAC address.

## 3.Network
Is where [[Routers|routing]] & re-assembly of data takes place. Routing determines the most optimal path in which these chunks of data should be sent.

The protocol for this are:
OSPF (Open Shortest Path First)
RIP (Routing Information Protocol)

They decide on the path checking some conditions like shortest path, path with less packet loss, faster physical connection etc.

Everything in this layer is dealt via IP addresses. Devices such as router capable of delivering [[Packets & Frames|packets]] using IP are known as layer 3 devices.

## 4.Transport
enables end to end communication between running apps on different hosts.
Transmits data across the network 
Two protocols:
- [[TCP]]
- [[UDP]]
## 5.Session

This layer creates and maintains the connection to other computer for which the data is destined. when a connection is established a session is created. whilst this connection is active, so is the session
Also closes the connection if lost or unused, a session can contain checkpoints where if the data is lost, only the newest pieces of data are required to be sent saving bandwidth.
Session are unique! data cannot travel over diff sessions.

## 6.Presentation
Standardization of data starts to take place.
acts as a translator for data to and from application layer. The receiving computer will also understand data sent to a computer in one format destined for in another format. ex when you send an email the other user may have another client, but the contents of the email still need to display the same.
Security features like encryption (HTTPS for example) occur at this layer.

## 7.Application
Layer in which protocols and rules are in place to determine how the user should interact with data sent or received.

![[Pasted image 20260310124352.png]]
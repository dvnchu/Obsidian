[[Redes]]
## TCP/IP
This protocol consists of four layers and is arguably just a summarized version of OSI.
- Application
- Transport
- Internet
- Network Interface
info is added to each layer of the TCP model as the [[Packets & Frames|packet]] traverses it (encapsulation).

it is connection-based, TCP must establish a connection between both a client and a device acting as a server before data is sent.

because of this TCP guarantees that any data sent will be received on the other end this process is called [[TCP#Three-Way handshake|Three-Way Handshake]]
process. 

| Advantages of TCP                    | Disadvantages of TCP                                                                                                        |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Guarantees data accuracy             | Requires a reliable connection.<br>If a small chunk of data is lost then the whole chunk cant be used.                      |
| Synchronizing devices                | A slow connection can bottleneck another device as the connection will be reserved on the receiving computer the whole time |
| A lot more processes for reliability | significantly slower than UDP because of this.                                                                              |
![[Pasted image 20251217183122.png|center]]


##### crucial TCP packet headers

| Header                    | Description                                                                                                                         |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Source Port               | Port opened by the sender to send the TCP packet from. randomly chosen                                                              |
| Destination Port          | Port number that an app or service is running on the remote host. Not random                                                        |
| Source IP                 | IP of the device sending                                                                                                            |
| Destination IP            | IP of the destined device                                                                                                           |
| Sequence Number           | When a connection occurs the first piece of data is a given random number                                                           |
| Acknowledgement<br>Number | Next piece of data, sequence Number +1                                                                                              |
| Checksum                  | A math calculation is made where the output is remembered. If the receiving device gets another result the data must be corrupt<br> |
| Data                      | Bytes of a file being transmitted                                                                                                   |
| Flag                      | This header tells how the packet should be handled by either device during handshake                                                |
###### Three-Way handshake

| Step | Message | Description                                                                                                         |
| ---- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| 1    | SYN     | initial packet sent by a client during a handshake. it is used to initiate a connection and synchronise two devices |
| 2    | SYN/ACK | sent by the receiving to acknowledge the synchro                                                                    |
| 3    | ACK     | used by either client or server to acknowledge a series of messages/packets have been succesfully revceived         |
| 4    | DATA    | Once established data is sent via this message                                                                      |
| 5    | FIN     | properly close the connection                                                                                       |
| $    | RST     | Abruptly ends all comm. indicates if there was some problem during the process.                                     |

![[Pasted image 20251217203546.png]]


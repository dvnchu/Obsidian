[[Redes]]
###### User Datagram Protocol
Stateless protocol that doesn't require a constant connection between the two devices for data to be sent (there is no handshake).

| Advantages of UDP                                                                                                    | Disadvantages of UDP              |
| -------------------------------------------------------------------------------------------------------------------- | --------------------------------- |
| Much faster                                                                                                          | Doesnt check if data is received  |
| Leaves the application layer to decide if theres<br>control over how quickly [[Packets & Frames\|packets]] are sent. | Flexible for software developers  |
| Does not reserve a continuous connection on a device                                                                 | Unstable connections are terrible |

it is useful when you need small pieces of data like in [[ARP]] or [[DHCP]] protocol or larger files like video streaming where its okay if data is lost as it just become a bit pixelated (pixels are lost pieces of data).

##### UDP packet headers

| Header                | Description                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Time To Live<br>(TTL) | expiry timer for the packet so it doesnt clog up yout network                                                       |
| Source Address        | The IP address of the device that the packet is being sent from                                                     |
| Destination Address   | The IP address of the device that the packet is being sent to                                                       |
| Source Port           | The port that is opened by the sender to send the UDP packet from- randomly chosen.                                 |
| Destination <br>Port  | This value is the port number that an application or service is running on the remote host. The one receiving data. |
| Data                  | this header is where data is stored                                                                                 |

![[Pasted image 20251218015904.png]]

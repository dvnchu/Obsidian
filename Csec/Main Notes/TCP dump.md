flags
-i choose interface
-w save captured files to a file
-r use tcpdump to read a packet
-c limit packet quantity
-nn dont resolve ip addresses and port numbers
-v verbose

## Filters
tcpdump host HOSTNAME

src host IP to limit from a particular source IP address

dst host IP to get packets sent to a destination

also you can limit to capture from a port
```shell-session
sudo tcpdump -i ens5 port 53 -n
```

protocol
```shell-session
sudo tcpdump -i ens5 icmp -n
````

Also you can use logical op
and or not

greater LENGTH
less LENGTH

man pcap-filter

you can filter based on the contents of a header byte to filter by protocol

proto[expr:size]
proto is protocol arp ether icmp ip ip6 tcp udp
expr indicates the bute offset
size indicates number of bytes tha interest us

- `ether[0] & 1 != 0` takes the first byte in the Ethernet header and the decimal number 1 (i.e., `0000 0001` in binary) and applies the `&` (the And binary operation). It will return true if the result is not equal to the number 0 (i.e., `0000 0000`). The purpose of this filter is to show packets sent to a multicast address. A multicast Ethernet address is a particular address that identifies a group of devices intended to receive the same data.  
    
- `ip[0] & 0xf != 5` takes the first byte in the IP header and compares it with the hexadecimal number F (i.e., `0000 1111` in binary). It will return true if the result is not equal to the (decimal) number 5 (i.e., `0000 0101` in binary). The purpose of this filter is to catch all IP packets with options.

you can use tcp[tcpflags]
- tcp-syn
- tcp-ack
- tcp-fin
- tcp-rst
- tpc-push

you can capture stuff with the concrete flags

customize how to show packets
-q: quick output
-e: Print the link-level header
-A: Show packet data in ASCII
-xx: Show packet in hex
-x: show headers and data in hex and ASCII
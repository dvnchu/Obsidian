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

-sn to discover live hosts


-St connect scan discover networks services listening on these ports
tries to complete TCP three-way handhsake with every target TCP port. if port is open and NMAP connects, Nmap will tear down the established connection

-sS SYN scan
stealth only sned a TCP syn packet so the handshake is never completed

-Su scans UDP services

Nmap allows you to limit ports

-F 100 most common
-p[range] scan between a range


-O enables OS detection it not perfectly accurate


-sV enables version detection for the services

-A enables os detection, version scanning and traceroute among other things


| Timing          | Total Duration |
| --------------- | -------------- |
| T0 (paranoid)   | 9.8 hours      |
| T1 (sneaky)     | 27.53 minutes  |
| T2 (polite)     | 40.56 seconds  |
| T3 (normal)     | 0.15 seconds   |
| T4 (aggressive) | 0.13 seconds   |

. The number of parallel probes can be controlled with `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>`

`--min-rate <number>` and `--max-rate <number>`. As the names indicate, they can control the minimum and maximum rates at which `nmap` sends packets

--host-timeout <time>

-v for verbosity vv vvv v2 v3 v4

-d for debugging level output also with levels

-oN normal output
-oX XML
-oG grepable output
-oA all major formats



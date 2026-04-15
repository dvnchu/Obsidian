tags: [[Redes]]

Determines what traffics is allowed to enter and exit.

Think of a firewall as border security for a network. An administrator can configure a firewall to permit or deny traffic from entering or exiting a network based on numerous factors such as:
- Where the traffic is coming from?
- Where is the traffic going to?
- What port is the traffic for?
- What protocol is the traffic using?

## Stateful firewalls

This type of firewall uses the entire information from a connection; rather than inspecting an individual packet, this firewall determines the behavior of a device **based upon the entire connection**.

This firewall type consumes many resources in comparison to stateless firewalls as the decision making is dynamic. For example, a firewall could allow the first parts of a [[TCP#Three-Way handshake|TCP handshake]] that would later fail.

If a connection from a host is bad, it will block the entire device.


## Stateless firewalls
This firewall type uses a static set of rules to determine whether or not **individual [[Packets & Frames#Packet|packets]]** are acceptable or not. For example, a device sending a bad packet will not necessarily mean that the entire device is then blocked.<br><br>Whilst these firewalls use much fewer resources than alternatives, they are much dumber. For example, these firewalls are only effective as the rules that are defined within them. If a rule is not exactly matched, it is effectively useless.<br><br>However, these firewalls are great when receiving large amounts of traffic from a set of hosts (such as a Distributed Denial-of-Service attack)



Firewalls work at layers [[OSI Model#2.Data Link|2]] & [[OSI Model#3.Network|3]] of the OSI Model.
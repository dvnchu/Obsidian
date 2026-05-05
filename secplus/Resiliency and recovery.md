High availabilty provides resiliency
Many differents components working together
But higher availability means higher cost

Server cluster is another option
Combine two or more servers that appear and operate as a larger server
more capacity and availabilty
often configured in os 
shared storage

Load balancing
One central load balancer to distribute the load between various servers
a server does not know others exist
can be different os
add or remove devices

Site resiliency(Physical)
Recovery site prepped
Move data center in case of a disaster
once disaster is over you can come back
types:
- Hot sites
exact replica
stocked with hardware
and data synched
up to date
- Cold site
empty building
you have to bring data equipment and people
- Warm site
Has just enough to get going

*Geographic dispersion* (place far from site in case of disaster)
*Platform diversity* (Have diff systems in case of a vulnerability) -> multi cloud systems
Continuity of operations planning(COOP) There needs to be an alternative to technology


# Capacity planning

*Match supply to the demand*
right ammount of people
appropiate tech
best infrastructure

Some services require human intervention
like a call center line
very difficult to manage resource
Too few or Too many

Technology
pick so it can scale enough
have load balancers multiple servers
sql clusters
split dbs 
etc

infrastructure
Underlying stuff
app servers network
CPU, network storage
Cloud-based/physical devices


# Recovery testing
Test before an actual event happens
Well-defined rules
specific scenario
evaluate response

Tabletop excersises
Go trough the stages not doing it phisically as it might be expensive

Fail over test
test the redundant infrastructure that might fail
routers firewalls switches
all workflow should be kept untouched


Simulation
phishing attack ,password request ,data breaches
test users and internal security


parallel processing
split a process trough multiple CPUs
if a processor has a problem you can split the load between the rest


# Backups 
IMPORTANT
many implementations
total amount of data
type of backup
backup media
storage location
software
day


backup categorys

Onsite 
No internet link required
data inmediately available
less expensive

offsite
transfer over internet or wan
data available after disaster
restoration can be performed from anywhere

frequency

Encryption
backups have sensitive info its dangerous if offsite
easy for attacker
encrypt to avoid this
recovery key required
useful for cloud backups

Snapshots
Popular on vm and cloud
instant backup of a system
save config and data
future snapshots contain just changes in between

Recovery testing
you have to be sure you can restore the data
perform periodic audits

Replication
data sync in multiple locations
available data
locally to all users
data recoverable

Journaling
if theres a problem while saving stored data is corrupt
recovery is complicated
before writing make a journal entry
Once journal is written then info can be copied
and via journal db checks if after a problem theres data thats missing so it can fill blanks


# Power resiliency
UPS uninterruptible power supply
short term backup power
types

offline/standby UPS -> battery backup
line-interactive UPS -> slowly increase if it sees a drop
on-line/Double-conversion -> always run from battery backup 

Generators
Long term power backup
fuel required
it  may take a few minutes to get up
battery ups while the generator starts
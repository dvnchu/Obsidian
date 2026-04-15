tags: [[web]]

Domain Name System, provides a simple way to communicate with devices on the internet without remembering long number chains. 

#### Hierarchy

#### Top-Level Domain 
Tryhackme **.com**

is the right hand part of a domain name.

There are two types (Generic Top Level) used to refer to the purpose and ccTLD (Country Code Top Level Domain) used for geographical purposes.

TLD list: https://data.iana.org/TLD/tlds-alpha-by-domain.txt

#### Second-Level Domain
**Tryhackme** .com
63 chars + TLD.

#### Subdomain
left-hand side of the Second-Level Domain separated by a period.
**Admin**. Tryhackme.com
Same restrictions as Second-Level
You can use multiple subdomains to create longer names.
but length must be kept to 253 chars or less.

### Record types

**A Record**: IPv4 addresses

**AAAA Record**: IPv6 addresses

**CNAME Record**: Resolve to another domain name (store.tryhackme.com returns a CNAME record shops.shopify.com)

**MX Record**: Resolve to the address of the servers that handle the email for the domain you are querying.

**TXT Record**: free text fields where any text-based data can be stored.


### DNS Request
![[Pasted image 20251218133358.png]]
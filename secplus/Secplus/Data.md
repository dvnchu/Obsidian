# Data types
**Regulated**
managed by a third party
Government laws and statues

**Trade secrets**
Secret from organizations unique to them

**Intellectual property**
public but protected by law

**Legal information**
Court records and documents
PII and other details
stored in many diff systems

**Financial information**
Internal company finances
customer financial
payment records


Human readable
Humans can understand

Non human readable
Not easily understood
encoded data
barcodes image

theres some hybrid formats like XML

Clasify sensitive data
Not all data has the same level of categorization for sec
diff process to view
diff networks zones

Classifications
- Propietary
Data that is property of an org
also may include trade secrets

- PII personally identifiable information
Name, birth, mothers maiden name, biometric info

- PHI protected health information
individual info
health status health care records
payments etc

levels of access
- Sensitive
- intellectual property, PII, PHI
- Confidential
- Public/unclassfified
- Private/classified/restricted
- Critical

# States of data
Data on a storage -> Data at rest
can be encrypted full disk/db/file or folder
apply permisions

data over the network -> Data in transit
Not much protection
can use firewall or Intruction prevention system
TLS (Transport layer security)
IPsec (Internet protocol security)

Data actively processed in memory -> Data in use
Ram Cpu cache
almost always decrypted

Sovereignty
Rules of a country apply to all data you have inside it
all monitoring or court orders will use that countrys law

GDPR
Data collected on EU must be stored in the EU

Geolocation
track people who has access to data 802.11, providers GPs
can be used to manage data access (where can people access)


# Protecting data
Geographic restrictions
Network location based on IP subnet (difficult on mobile devices)

GPS
802.11 wireless, less accurate
IP address not very accurate
 Geofencing automatically allow or restrict access when user is in a certain location

Data is one of most important assets for a company
It is eeverywhere storage network cpu etc


Encrypting data
encode info into unreadable data
Hashing data
Obfuscation (turn readable code into nonsense helps for security holes)
Data masking
tokenization
Segmentation (separate data in various dbos)
Permission restrictions
---
id: "1.4"
aliases: []
tags: []
---

# Public Key Infrastructure(PKI)
*Policies and procedures responsible for creating distributing managing storing and revoking digital certs**
Also refers to the binding of public keys to people or devices

**Symmetric encryption**
A single shared key, Encrypt with the key, Decrypt with the key
doesnt scale very well
very fast

**Asymmetric encryption**
Encrypting with one key
Decrypting with another key
They are mathematically related

- One private key and one public key
The private key is the only key that can decrypt data encrypted with the public key
Theres no way to reverse engineer the private key from the public key.

PGP GPG

Build both the public and private key at the same time,
Lots of randomization primer numbers and math

* Key escrow 
	in big orgs Someone holds your decryption keys and not the person that encrypted the data.
	This can be a legitimate arrangement

# Encrypting data

**Files Encryption** 

* Full disk and partition
	Bitlocker, FileVault
* File encryption
	EFS(Encrypting file system)
	3rd party

**Protecting stored data**

* Transparent encryption: encrypt all database with a symmetric key
* Record level encryption: Encrypt individual columns separate symmetric keys per column

**Transport Encryption**
Protect data traversing the network

- Encrypting in the application
- VPN(Virtual Private Network) (it provides an encrypted tunnel regardless of the app)
	 * Client-Based VPN using SSL/TLS
	 * Site-To-Site VPN using IPsec

**Encryption  Algos**
Both sides decide on the algorithm before encrypting the data
Some are more secure faster, more complex etc
algo is usually a known entity
but you cant reverse wihtout the key

the key determines the output
- encrypted data
- hash value
- digital signature

Symmetric 128bit or larger are considered safe

asymmetric common to see key of 3072 bits or larger

A weak key is a weak key but you can make it stronger with multiple processes
**key stretching/strengthening**


# Key exchange

How do you share an encryption key without transferring it insecurely

Out-of-band key exchange
Dont send the symmetric key over the net

In-Band
Protect with additional encryption
asymmetric encryption to deliver a symmetric key

Theres a need for fast security 
Keys used for short periods of time
like sessions keys that just work for a session
share a symmetric session key using asymmetric encryption

Use public and private key cryptography to create a symmetric key
![[Pasted image 20260408193039.png]]

!Diffie hellman chaval


## Crypto hardware
### Trusted platform module (TPM)
Specification for cryptographic functions
its a cryptographics processor
rng key gen
Persistent memory
keys burned in during manufacturing
Versatile memory
Storage keys hardwarer info
Stores bitlocker keys
password protected


### Hardware Security Module (HSM)
Used in large envs
Clusters redundant power
Securely store thousands of cryptographic keys

high end cryptographic hardware plug-in card or separate hardware device

secure storage of keys also allows for a backup

cryptographic accelerators can be used.

## *Secure enclave*
a hardware processor isolated to the main one
Provides extensive security features
own boot ROM
monitors boot process
True random number gen
real time encryption
root cryptographic keys
performs AES encryption in hardware

## Key management systems
Centralized key management system 
on premises or cloud based
manage all keys from one console and keep all keys separate from the data
create keys for a service or cloud
associate key user
rotate keys on regular intervals
log key use and important events

# Obfuscation
making something unclear but not impossible to understand hide in plain sight
steganography
Network based
- embed messages in TCP packets
- Use an image
- invisible watermarks
- Audio steganography
- Video steganography

## Tokenization
Replace sensitive data with a non sensitive placeholder, a token

Common with credit card processing
it uses a one time use token, so its not encryption or hashing


# Hashes
Represent data as a string of text
you cant recreate data when all you have is a hash
used to store passwords confidentiality

Authentication no repudiation and integrity


**SHA256**
256 bits/64 hexa

The hash should be unique diff inputs shouls never create the same hash, if they do its a collition
MD5 collision problem 
**Practical hashing**
- Verify a download file
- Password storage (salted hash, compare hashes during auth process nobody knows pass)
	Salt random data added to a password when hashing in case of repeated
	Rainbow tables wont work with salted hashes

Digital signatures
provide integrity
prove source of message
Person signing the document uses the private key to sign
Other people can verify that the private key was used with the public key to check if it was actually the person

# Blockchain technology
a distributed ledger
keeps track of individual transaction
anyone participating can mantain and everyone has a copy

- payment processing
- digital identification
- supply chain monitoring
- digital voting


transaction info is sent to everyone in the blockchain(nodes) info is added in a block containing recently verified transactions and its closed with a hash calculated from the previous block
and the copy of the block is sent to everyone
if someone modifys a transaction you can see that the hash is invalid

# Certificates
Public key cert
binds a publick key with a digital signature and details about the key holder
signature adds trust
PKI uses cert auth for additional trust
web of trust multiple individuals signing each other

can be built into the OS
Windows domain sevices

x.509
details
- serial number
- version
- signature algorithm
- issuer
- name of cert holder
- public key
- extensions
- etc..

Root of trust
inherently trusted component
hardware software firmware
Hardware security module (HSM), secure enclave, certificate authority

Browser has a list of certificate authorites included
you can purchas your web site validation for a certificate from a CA
it shows that you are truly the owner of your website

z
You can be your own CA (private certificate authorities)

build in house
devices must trust the internal CA
relatively common for medium-to-large organizations

Windows cert services, Open CA

Wildcard certificates
Extension to x.509
allows a certificate to support many different domains

the CA can have a certificate revocation list (CRL)

OCSP stapling
Online certificate status protocol
scalability for the checks
have the certificate holder verify their own status
status is stapled into the ssl tls handshake
digitally signed by the c#@@a

browser checks for evocation(not all of them)
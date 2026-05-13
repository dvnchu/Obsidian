symmetric enc standards
DES 1977 56 bit broken in less than 24 hours
3DES DES 3 times 168 bits effective security of 112 bits deprecated 2019
AES adopted in 2001 key size of 128 192 or 256



assymetrics standars
RSA
Diffie-Hellman
Elliptic curve cryptography

## RSA


Bob choses two primer *p* and *q*; n = pxq

phi(n) = n - p - q + 1 Bob selectes e relatively prime to phi(n)
He then select d where exd = 1, mod phi(n)

public key is (n,e)
private key is $(n,d)


We encrypt x alice would calculate and send y = x^e mod n 

Bob will decrypt the received value by calculating x = y^d mod n 

## Diffie Hellman key exchange
establish a shared secret between to parties over an insecure communication channel

1- Alice and Bob agree on public variables: Large prime p and a generator g where 0 < g < p publicly disclosed values

2- Each party choses a private integer each value is a **Private key**

3- using key in step 2, and public variables each party calculates their private key. 
Alice calculates a = g^a mod p
Bob calculates B = g ^b mod p

4- Bob receives A / Alice receives B; This is the key exchange

5 - They can finally calculate the shared secret using the received public key and their own private key
Alice calculates B^a mod p
Bob calculates A^b mod p
both calculations yield the same result G^ab mod p = 10

Often used alongside RSA public key cryptography.

## SSH
### Auth
Username and passwords are not the best security practices for ssh

at some point one will surely hit a machine with ssh configured with key auth

ssh-keygen generates key pairs
 
 Specifies the type of key to create. The possible values are “dsa”, “ecdsa”, “ecdsa-sk”, “ed25519”, “ed25519-sk”, or “rsa”.

you can choose the algorithm 

You should never share ssh keys

~/.ssh is the default place to store these keys for OpenSSH
authorized_keys file holds public keys that are allowed access to the server if key auth is enabled


on ctfs ssh keys are an excellent way to upgrade a reverse shell


## PGP and GPG

PGP stands for Pretty Good Privacy implements encryyption for files, digital signing and more
GPG is an open source implementation of the OpenPGP standard
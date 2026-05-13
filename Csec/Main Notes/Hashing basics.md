With hashing ther is no key and its meant to be simpossible to go from the ouput to the input
Any modification on the input change the output

Hash collition
A collition is when two different inputs give the same output

md5sum
sha1sum
sha256sum
sha512sum

Recognising hashes

on linux password hashes are stored in /etc/shadows
encrypted password field contains the hashed passphrase with four components \$prefix\$options\$salt\$hash



|Prefix|Algorithm|
|---|---|
|`$y$`|yescrypt is a scalable hashing scheme and is the default and recommended choice in new systems|
|`$gy$`|gost-yescrypt uses the GOST R 34.11-2012 hash function and the yescrypt hashing method|
|`$7$`|scrypt is a password-based key derivation function|
|`$2b$`, `$2y$`, `$2a$`, `$2x$`|bcrypt is a hash based on the Blowfish block cipher originally developed for OpenBSD but supported on a recent version of FreeBSD, NetBSD, Solaris 10 and newer, and several Linux distributions|
|`$6$`|sha512crypt is a hash based on SHA-2 with 512-bit output originally developed for GNU libc and commonly used on (older) Linux systems|
|`$md5`|SunMD5 is a hash based on the MD5 algorithm originally developed for Solaris|
|`$1$`|md5crypt is a hash based on the MD5 algorithm originally developed for FreeBSD|

MS windows passwords are hashed using NTLM passwords are stored in the SAM. tools like mimikatz circumvent it. Hashes are split into NT hashes and LM hashes

https://hashcat.net/wiki/doku.php?id=example_hashes
man 5 crypt

Password Cracking
GPUs are good at some math calculations involved in hash functions
some algos like Bcrypt are designed so that hashing on a GPU does not provide speed improvement


cracking on vms is worse as there is no gpu access normally
hashcat will be worse
John the ripper uses CPU and works in a VM out of the box but you may get better speed on host


Hashcat uses the following basic syntax: `hashcat -m <hash_type> -a <attack_mode> hashfile wordlist`, where:

- `-m <hash_type>` specifies the hash-type in numeric format. For example, `-m 1000` is for NTLM. Check the official documentation (`man hashcat`) and [example page(opens in new tab)](https://hashcat.net/wiki/doku.php?id=example_hashes) to find the hash type code to use.
- `-a <attack_mode>` specifies the attack-mode. For example, `-a 0` is for straight, i.e., trying one password from the wordlist after the other.
- `hashfile` is the file containing the hash you want to crack.
- `wordlist` is the security word list you want to use in your attack.


Integrity checking
Hashes can be used to check that files havent been changed 
it also can be used to find duplicate files; if Two docs have the same hash they are the same document


HMACs
keyed-hash Message authentication Code is a type of message authentication code (MAC) that uses cryptographic hash function in combination with a secret key to verify authenticity and integrity

![[Pasted image 20260513154944.png]]

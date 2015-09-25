% Cryptography in Practice
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Cryptography

- Defined
- The act or art of writing in code or secret characters; also, secret characters, codes or ciphers, or messages written in a secret code.
- [1913 Webster +PJC]
- Used in computer security primarily for C & I of CIA triad

# Crypto quote

- "Cryptography doesn't solve problems...
- it just moves them somewhere else."

# Type of Crypto

- One-way encryption
- Two-way encryption

# One-way crypto

- aka hashing, digest
- No enc key, can't be reversed
- input size varies, output is of equal size

# Two-way crypto

- aka reversible encryption
- key is used to encrypt/decrypt
- input size varies, output size varies

# Crypto hashing functions

- Purpose: reduce variable sized input to a fixed size output
- Algorithms: MD5, SHA-1, SHA-256, SHA-512
- Theoretically should be free of collisions

# Hash Examples

- Given string "OWASP Testing Guide"
- MD5: d38b191db72fffe79ff8233fea50af43
- SHA-1: 81149b15086f3ce40f844a147646c863c000ed6d
- SHA-256: e305129150f218d5f79d34021c99f12979bc9cdb2cdd1720e7a0253c4764c6de
- $ echo -n "OWASP Testing Guide" | sha256sum 

# Hash diagram

![One-way hash](http://images.books24x7.com/bookimages/id_35308/ns780412.jpg)[1]

# Message Authentication

- Utilizes crypto to prove 
- (1) Message hasn't been altered
- (2) source of the message - non-repudiation
- Scheme determines if (1), (2) or both apply

# Message Auth-n

- Could use symmetric crypto to encrypt full message
- Send message, transfer key via alternate channel
- Has problems - key transfer, block reordering, replay/forge

# Message Auth-n

- Most schemes don't include encrypting the message
- Transport layer or other means to hide message contents
- Add a bit of data to the message to do Auth-n
- Computationally cheaper, allows 1 to many, pushes auth-n check to client

# MAC

- Message Authentication Code
- Run message through a MAC algorithm and concatenate output to message
- Receiver can pull off MAC, re-run algorithm and compare

# MAC diagram

![MAC diagram](http://minnie.tuhs.org/NetSec/Slides/Figs/w3s1.jpg)[2]

# Types of MAC

- Symmetric Encryption
- Hash message, encrypt has with symmetric crypto, append to message
- Receiver strips MAC, decrypts to get hash.  Re-hash and compare
- Assumes key safely shared between sender/receiver 

# Types of MAC

- PKI - public key cryptography
- Same as symmetric except private key encrypts, public key decrypts
- Solves the key sharing problem

# S & P MAC

![Crypto and MAC](http://minnie.tuhs.org/NetSec/Slides/Figs/w3s2.jpg)[2]

# Types of MAC

- Shared Secret
- Before sender hashes, appends secret to message, then simple hash of that
- Message (minus secret) + hash are sent
- Receiver adds secret before creating hash to check
- Share Secret acts like a salt used for password hashes

# Shared Secret MAC

![Shared Secret](http://minnie.tuhs.org/NetSec/Slides/Figs/w3s3.jpg)[2]

# Uses of Hashes

- Password hashing (already covered)
- File integrity checks
- Message Authentication

# Two-way Crypto

- Input: Plaintext, key, cipher
- Output: Cipher text
- Plain text + key + cipher = cipher text
- Cipher text + key + cipher = plain text

# Two-way Crypto

- Symmetric encryption
- Asymmetric encryption 

# Two-way Crypto

- Symmetric key encryption
- Shared key/secret between parties
- Difficult to share keys esp with larger groups
- Computationally cheap
- e.g. AES (Rijndael, DES3, Twofish, Blowfish, IDEA, ...

# Two-way Crypto

- Asymmetric encryption aka PKI
- Public/Private key pairs, key mgnt easier
- Computationally expensive
- e.g. PKI, OpenPGP, GPG, RSA, ElGamal

# Symmetric Crypto

![Decoder Ring](https://upload.wikimedia.org/wikipedia/commons/5/5b/Captain-midnight-decoder.jpg)[4]

# Symmetric Crypto

![Symmetric Crypto](http://images.books24x7.com/bookimages/id_35308/ns780410.jpg)[1]

# Asymmetric Crypto

- Works like Symmetric except two keys are used
- Plain text + PubKey + Cipher = Cipher Text
- Cipher text + PrivKey + Cipher = Plain Text
- Can be reversed - aka enc with PubKey or PrivKey
- Whatever key encrypts, its pair is used to decrypt

# Asymmetric Crypto

![PKI](http://core0.staticworld.net/images/idge/imported/article/nww/2008/10/02fig02-100277994-orig.jpg)[5]

# Digital Signatures

- Encrypting with PrivKey can prove authorship, only PubKey will decrypt
- Assumes author ONLY has control of PrivKey
- Digital signature - hash message & encrypt hash with PrivKey, append MAC
- Receiver can verify hash and that PrivKey had to encrypt

# Digital Signatures

![Digital Signature](http://www.herongyang.com/PKI/Digital-Signature-Scheme.jpg)[6]

# /dev/random

- Random numbers used in many crypto algorithms
- e.g. RSA public-key enc, stream key for symmetric stream ciphers, ...
- Computer don't do random very well
- Random requires
- Uniform distribution: frequency of number repeats should be the same (or close)
- Independence: Generated value has no relationship to the one before or after

# Generating random

- pseudorandom number generators
- algorithm to generate numbers of reasonable randomness
- TRNG - True Random Number Generator
- use nondeterministic source to generate random values
- leaky capacitors, thermal noise, light jitter, ...

# Threats to Crypto

- Brute force attacks
- Cryptanalysis - Frequency analysis, known plaintext, chosen cipher text, ...
- Information leakage - only important stuff is encrypted, meta-data analysis
- Physical
- Implementation bugs, poor source of random data
- Humans (Social Engineering)

# Threats to Crypto

![Pragmatic Crypto](http://imgs.xkcd.com/comics/security.png)[3]

# Using Crypto

- For the following, what makes sense for that type of crypto

# Symmetric Crypto

- Credit Card Number
- Yes
- Password
- No
- Email address
- Maybe, depends on use case

# Symmetric Crypto

- Blood Type
- Yes
- Session key
- No
- Student ID
- Maybe, depends on regulations and its use case

# Symmetric Crypto

- Appropriate for protecting data that an application will need to use at some point in the future

# Asymmetric Crypto

- RESTful Web Service
- Yes
- SOAP Service
- Maybe, other standard exist for this
- Credit Card Numbers
- Maybe, depends on use case

# Asymmetric Crypto

- AJAX Call
- Maybe, depends on use case
- Logging Routine
- Yes
- Student ID
- Maybe, depending on regulations and its use case

# Asymmetric Crypto

- Appropriate for protecting data that must travel over an insecure link between systems

# Hash Functions

- Password
- Yes
- Phone Number
- Maybe if used for lookup/matching later
- Order Total
- No 

# Hash Functions

- SSN
- Maybe if used for lookup/matching later but subject to precalc attacks
- Address
- No
- UUID
- Yes, hashing used in Version 3 & 5 UUIDs

# Hash Functions

- Appropriate for data that the application needs to verify rather then use in computation

# Mixing Crypto

- SSL mixes crypto types for efficiency
- Uses PKI to safely share a symmetric key
- Computationally expensive, key sharing not a problem
- Afterwards, shift to symmetric only
- Computationally cheap, key shared PKI

# Questions

- Ask now...
- or later on Piazza

# How to Find me

- Office: Gates 6.706
- Generally in the office Tuesday/Thursday mid-morning until class
- Post questions to Piazza 
- https://piazza.com/utexas/fall2015/cs361/home
- Course Canvas site
- https://utexas.instructure.com/courses/1144129#

# Readings 

- Exam question may be source from any of these readings...
- Look for "Cryptography in Practice" in the Lecture notes page on the class Canvas site.
 

# References 

- [1] Image from: http://ciscodocuments.blogspot.com/2011/05/chapter-04-fundamentals-of-cryptography.html
- [2] Image from: http://minnie.tuhs.org/NetSec/Slides/week3.html
- [3] Image from: https://xkcd.com/538/
- [4] Image from: https://en.wikipedia.org/wiki/Secret_decoder_ring
- [5] Image from: http://www.networkworld.com/article/2268575/lan-wan/chapter-2--ssl-vpn-technology.html
- [6] Image from: http://www.herongyang.com/PKI/Digital-Signature-Word-What-Is-Digital-Signature.html

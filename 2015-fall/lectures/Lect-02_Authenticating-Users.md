% Authenticating Users
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Authenticating Users

- Fundamental part of computer security
- Required for access control & audit
- Computers are not good at this

# Basic steps in auth

- Identification step
- Identifying yourself to the system
- Verification step
- Providing something that 'proves' your identity claim

# Identity

![Identity](http://www.explainxkcd.com/wiki/images/7/74/identity.png)

# Other Auths

- Message Authentication
- Proving a message came from a party 
- and its not been altered
- That's not what we're talking about today

# Factors of auth

- Something you know
- Something you have
- Something you are

# More factors?

- Something you are
- Static biometrics - don't change (mostly)
- fingerprint, face, retina, hand geometry, ...
- Dynamic biometrics - measure something 'in motion'
- typing pattern, signature, gait (how you walk), ...

# Weakness of the factors

- Something you know 
- forget it
- attacker guess it
- choose poorly

# Weakness of the factors

- Something you have
- lost, left in a cab
- APT gets your algorithm (cough RSA)
- attacker clones or forges a token

# Weakness of the factors

- Something you are
- Cannot easily change your fingerprint
- or your eyes
- injury - loose that something
- cannot revoke your eyes
- tricky to get this right 

# Most common factor

- ...
- Yeah, password-based auth

# Pass auth

- Take the username + password
- verify that both match what is stored
- access granted

# Once your proven

- system uses your identity for role / group membership
- determines if access is allowed
- A part of discretionary access control

# Discretionary access control

- granting/restricting access based on identity/group membership
- more on this later

# Problems with password auth

- Brute force aka guessing
- single user vs password list
- multiple users vs top N passwords
- user enumeration vuln makes this far easier

# Brute force countermeasures

- Account locks
- Soft lock
- Hard lock
- Escalating time out

# Problems with password auth

- Offline dictionary attack
- Gain password store, precalculate hashes
- Rent some cloud processing

# Problems with password auth

- shoulder surfing
- walk away from laptop
- malware on laptop
- capture the act of entering password

# Problems with password auth

- sticky note under keyboard
- same password EVERYWHERE
- easily guess password

# Problems with password auth

- Ask the user for it
- Social engineering
- Phishing / Fake login / XSS on login

# Problems with password auth

- Transmit password in the clear
- Cached or otherwise stored
- Cold boot attacks

# Counter measures for pass auth

- complexity requirements
- multiple browsers
- two-factor auth (more later)

# Strength

![Password Strength](http://imgs.xkcd.com/comics/password_strength.png)

# Demo time

- Show that password fail example here

# Password storage

- char or varchar in database
- cookies / browser local storage
- sqlite database on file system
- please don't do these things

# Hashing

- Take a hash (one-way function) of the password
- Store this
- Take entered password, hash and compare
- MD5 was commonly used for this

# Hashing problems

- Can pre-calculate large lists of hashes
- Services provide lookups
- Google the hash
- same password, same hash

# Salting your hash

- Counter measure for the pre-compute problem
- Add a random nonce/salt to the password and then hash
- Store the hash and salt in the password store
- Must now pre-compute each hash if discovered

# Rounds of hashing

- Modern methods use rounds of hashing
- aka work factor - should be variable
- should be app configurable - will change over time

# Adaptive one-way functions

- return [salt], 2wayfunct([salt], [credential], c=[number of rounds]
- bcrypt, scrypt, pbkdf2
- choice can be on non-technical basis

# Other hashing benefits

- Hashing vs SQL Injection
- Hashing and DB indexing

# Other password stupids

- Limiting the length of a password
- Within reason - Django DOS
- No design/plan for compromise
- Encoding != hashing

# Other countermeasures

- Password audits
- Password managers
- Two accounts to exchange for services

# Attacks on passwords

- Guessing/brute force
- Pre-calculate hashes - simple lookup
- Rainbow tables - optimized lookup

# Legacy password policies

- Password rotation & history
- long-lived long passphrase better the rotated short password
- original design was rotation was shorter then crack time
- Cloud and GPU have made that laughable

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
- Look for "Authenticating Users

# References 

- None this time

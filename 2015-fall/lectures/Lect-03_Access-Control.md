% Access Control
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Access Control

- Access Control (from lecture 01)
- limiting access to users based on identity, role, etc 
- central to computer security

# Access Control

- unauthorized users 
- prevent them getting access
- authorized users 
- prevent them from using system in ways not allowed

# Back to Auth-N

- Remember authentication?
- Verify that someone is who they claim to be
- Prerequisite for access control

# Auth-N vs Auth-Z

- Auth-N == Authentication
- Auth-Z == Authorization
- Authorization - granting permission to something

# Back to Access Control

- A policy that states who/what may access a specific resource
- AND the type of access allowed
- e.g. read, modify, delete

# Audit

- For access control,
- Review of logs/actions of users to check policy is working
- Independent group/business unit
- Can also detect breaches, recommend changes to policy/process

# Access control

- Sits between Auth-N and the actual resource
- Brokers that connection, allowing access per policy
- Policy store holds info to determine access
- Can be as simple as file permissions

# Types of Access Control

- Discretionary Access Control (DAC)
- Mandatory Access Control (MAC)
- Role-based Access Control (RBAC)

# DAC

- Control based on identity of user + access rules
- e.g. file ownership - a user owns file and decides access
- Discretionary because owner can choose to provide access or not

# MAC

- Control based on labels applied to system resources
- Resources can be files, processes, network ports, ...
- Mandatory because label policy is enforced by kernel not users
- More on this in later - Multi-level Security Models

# RBAC

- Control based on roles users have in system
- e.g. Reviewer, Editor, Publisher, ...
- policy store holds map of role to access granted

# DAC vs MAC vs RBAC

- DAC is most common
- A single system can have multiple implemented
- e.g. SE Linux - DAC + MAC depending on MAC policy

# Properties of Access Control

- Relies on valid input to make its decision
- Auth must get things right
- Other factors could also be in play
- e.g. IP address, hostname, ...

# Access Control Props

- Least Privilege
- Provide only required access and no more
- Limits damage potential of actions - malicious or accidental
- Requires you know up front what is required

# Access Control Props

- Fail closed
- Default action should be to deny access
- If ! allowed, deny
- Closed policy vs open policy

# Access Control Props

- Separation of Duty
- Divide a process among multiple parties
- Single person cannot bypass process
- Access based on prior actions/history
- Forces collusion to be subverted

# Access Control Props

- Fine and coarse controls
- Fine/detailed access to constrain individual access
- Think DB row or cell restrictions
- Coarse access makes admin significantly easier
- Think access to whole database

# Access Control Props

- Conflict resolution
- Two policies combine to produce a conflict
- One allows, other denies
- Process to resolve these must be in place

# Access Control Props

- Policy store
- Administrative area where policies are stored
- Used by access control to make enforcement decisions

# Access Control Props

- Dual Access
- Requires 2+ people to act together
- e.g. Launch nuclear missiles
- Usually in high security systems only 

# Bits of Access Control

- Subject
- the thing that wants access
- Usually a process acting for a user
- Subject is what is audited

# Subjects

- Owner 
- Creator of a resource
- System resources are owned by admin user - system / root
- Can be assigned in DAC

# Subjects

- Group
- A collection of users form a group
- Multiple membership is common
- Allows for bulk/coarse control decisions

# Subjects

- World / Everyone / Anonymous
- Any process/user that can access that system
- May even be over a network

# Bits of Access Control

- Object
- The resource being accessed
- Files, directories, network ports, processes, memory, ...

# Access to an object

- Access right
- how a subject interacts with an object
- Read (copy/print), Write, Execute
- Delete, Create, Search (list)
- Write can act like delete in some cases

# ACLs

- Access Control Lists (ACL)
- Lists user and access allowed
- Default exists for those not in list

# Protection Domains

- Group of objects and the group's access rights
- Unix - user space vs kernel space
- Broad categories to constrain classes of subjects
- Used in containers like Docker

# Back to Auth

- Missed these bits in Lecture 02

# Token-based Auth

- Memory cards
- Store only - no processing
- e.g ATM card
- Usually combined with a PIN or password for 2 factor

# Memory Card Problems

- Need a reader
- Loss of card means loss of access
- Not very common for computer access

# Smart Card

- Memory and processing
- Dynamic generation - generate a unique value per time interval
- Challenge-Response - system produces a challenge, card does response
- Usually use PKI - card has private key

# Biometrics

- Left one thing out of Lecture 02

# Problems with biometrics

- Enrollment
- Associate a user with their biometric identifier
- Accuracy
- Match must be fuzzy enough but not too much

# Problems with biometrics

- Replay
- Capture bio identifier and use it again
- Usually involves skimmer or other means to capture biometric
- Denial-of-Service
- Purposefully fail to lock out a user

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
- Look for "Access Control" in the Lecture notes page on the class Canvas site.

# References 

- None at this time

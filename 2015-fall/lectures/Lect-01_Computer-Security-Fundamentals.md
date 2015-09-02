% Computer Security Fundamentals
% Matt Tesauro
% CS 361 - Lecture 01 

# Computer Security Defined

- Wikipedia says 
- "also known as cybersecurity or IT security, is security applied to computers, computer networks, and the data stored and transmitted over them." [1]

# Computer Security Defined

- NIST says 
- "Measures and controls that ensure confidentiality, integrity, and availability of 
information system assets including hardware, software, firmware, and information being processed, stored, and communicated. [2] 

# CIA Triad

- NIST used Confidentiality, Integrity and Availability in their definition
- Commonly known as the "CIA Triad"

# Confidentiality

- Ensures that data is not disclosed to unauthorized individuals
- Includes privacy aspects of controlling what information is collected by whom

# Integrity

- Two areas of concern - system and data
- System - ensure that the system can perform its function without being impaired deliberately or accidentally
- Data - ensure that data and programs are changed only by approved people/processes

# Availability

- Ensures that the system is available to its user base and that legitimate users have access

# CIA Triad

![CIA Triad](https://raw.githubusercontent.com/mtesauro/ut-cs-361/master/2015-fall/lectures/images/CIAJMK1209-resized.png)

# Scope of Info Sec

- What can fit under CIA?
- What doesn't fit under CIA?

# Confidentiality Issues

- Forced Browsing, Malware, Snooping, ...
- Attachment whoops, wrong fax number, leaving docs in copier or on desk
- Phishing, Social Engineering
- Anytime someone can access data they shouldn't, confidentiality issue.

# Ingegrity Issues

- CSRF, Direct Object Reference, Injection attacks...
- Malware, Malicious file execution, ...
- Many attacks are a 'one to many' issue
- If data can be modified when it shouldn't, integrity issue.

# Availability Issues

- DOS, DDOS are the obvious
- Malicious file execution, long running processes, breaking parsers, XML attacks...
- Not just crashing an app - could apply to data or a subset of users
- If a system cannot provide its promised service when requested, availability issue.

# What to protect

- Asset???
- The hardware, software and data that make up a computer system
- Includes the network and gear used by that system
- Assets are at risk because of a threat exercising a vulnerability

# Threats

- A potential for harm to CIA - violation of the security of a system
- Threats are conducted by Adversaries - those that attack a system
- Attack is an action against a system from an intelligent threat
- Script-kiddies and automated attacks are the background noise of the Internet

# Risk vs Vulnerability

- Risk is the likelihood or probability that harm will occur
- Vulnerability is a weakness that represents potential harm 

# Policy and Counter measures

- Security policy defines how security services are provided
- Counter measure - something that removes or limits the harm caused by an attack
- Limits by preventing or detecting an attack for quick recovery

# Attacks

- Active vs Passive attacks
- External vs Internal attacks
- Traffic analysis esp only encrypted messages

# In summary...

- A risk is the chance a vulnerability is successfully attacked by a threat

# Death Star Threat Modeling

![Death Star Exhaust Port](https://raw.githubusercontent.com/mtesauro/ut-cs-361/master/2015-fall/lectures/images/040808_2304_deathstarth1.jpg)

# Death Star TM

- Vulnerability 
- the 2 meter-wide thermal exhaust port leading to the reactor

# Death Star TM

- Threat 
- the Rebel Alliance's X-wing fighters

# Death Star TM

- Risk 
- the chance that a small fighter could successfully put a proton torpedo into the exhaust port

# Death Star TM

- Counter Measure
- Tie fighters and turbo-lasers

# Methods of protecting CIA

- Generally broken into 
- Technical controls - those involving technology
- Non-technical controls - those involving management techniques

# Tech Controls

- Access Control
- limiting access to users based on identity, role, etc 
- Proactive countermeasure

# Tech Controls

- Authentication
- Identifying or verifying the identity of computer users
- Prerequisite for many other areas - access control, audit, ...
- Proactive countermeasure

# Tech Controls

- Audit
- Create, maintain and review logs of system use
- Mostly a reactive countermeasure

# Tech Controls

- Incidence Response
- Monitor and react to violations of security policies or attacks
- Reactive countermeasure 

# Tech Controls

- System configuration and maintenance
- Keeping systems patched with latest software
- Deploying systems that are hardened against attack
- Proactive countermeasure

# Tech Controls

- System monitoring
- Also a general operations function
- Understand what normal is so abnormal can be detected

# Non-Tech Controls

- Physical security
- Limit physical access to computer systems
- Provide stable supporting infrastructure - power, cooling, etc

# Non-Tech Controls

- Security Planning
- Define the controls required and policies for users of computer systems
- Includes disaster recover planning

# Non-Tech Controls

- Training and Awareness
- Ensure users have an understanding of risks, laws, policies, etc.
- Sometime mandated by regulation or industry standards

# Non-Tech Controls

- Vendor management
- Ensuring 3rd party systems meet org standards
- Maintain support contracts and licensing

# Security Strategy

- Policy
- Implementations of that policy
- Verification that policy is working
- Working includes implemented correctly and effective for goal

# Policy

- Takes value of asset into account
- Looks at likelihood of attacks and threat actors
- Any inherent vulnerabilities with the system
- Usability vs Security
- Recovery vs Security costs

#  Policy Goals

- Prevention - avoid successful attacks
- Detection - quickly discover attacks in progress
- Response - react to an attack to mitigate or stop
- Recovery - clean up after an attack

# Verification

- Audit can determine if controls are done correctly
- Formal accreditation schemes exist for govnt and industry
- Assurance determines confidence that policy works as intended

# Wrap up

- Much of computer security seems simple at first
- Trade-offs are always an issue, usability, scalability, time to market, ...
- Security controls can be mis-applied for false sense of security
- Market & Government are considering liability for software security

# After Party

- Security Engineering, 2nd Edition
- http://www.cl.cam.ac.uk/~rja14/book.html
- Great book if your curious about the subject

![Security Engineering, 2nd Edition](https://raw.githubusercontent.com/mtesauro/ut-cs-361/master/2015-fall/lectures/images/book2coversmall.jpg)

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
- http://www.open.edu/openlearn/science-maths-technology/computing-and-ict/introduction-information-security/content-section-0  **NOTE:** Skip the "Activity" sections
- https://github.com/dnlongen/InfosecDictionary/blob/gh-pages/README.rst
- https://en.wikipedia.org/wiki/Computer_security
- http://www.wired.com/2015/01/security-predictions-2015/
- http://www.verizonenterprise.com/DBIR/2015/
- http://www.webopedia.com/TERM/S/security.html

# References 

- [1] https://en.wikipedia.org/wiki/Computer_security
- [2] http://nvlpubs.nist.gov/nistpubs/ir/2013/NIST.IR.7298r2.pdf

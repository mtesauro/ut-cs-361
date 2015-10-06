% Network Security
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Network Security

- Defined
- Network security consists of the policies adopted to prevent and monitor authorized access, misuse, modification, or denial of a computer network and network-accessible resources.
- Wikipedia [1]

# Network Security

- Defined #2
- Maintain the CIA triad on a network

# Network Security

- The single, most impacting network security change?
- Segmentation
- Divide the network into smaller networks plus understand/control access between networks.

# Firewalls

- Used to selectively allow access from one network to another
- Generally used as a edge device to separate internal LAN from the Internet or DMZ from Internet
- Only traffic allowed by policy/configuration is permitted in/out of network

# Firewalls

- Choke point for network
- Needs to be highly available and fault tolerant
- Needs to be hardened from attacks, especially external ones

# Firewall 

![Firewall Diagram](https://upload.wikimedia.org/wikipedia/commons/5/5b/Firewall.png)[4]

# Alternates

- Gateway router 
- Makes a great blunt filter
- e.g. Port 135 - 139 UDP/TCP & 445 UDP/TCP
- Fine grained rules at firewall behind gateway router

# Access Control with FW

- Service control
- IP, Port, Protocol restrictions to enable/disable services allowed
- Direction
- Inbound or outbound traffic restrictions

# Access Control with FW

- User control
- Determine what users/groups can do based on their identity
- Especially internal users as most externals won't be identified
- Application-specific control
- Filter inbound SPAM or control access to a portion of a website

# FW Benefits

- Single choke point to control traffic - reduces complexity
- Events can be logged and monitored
- Ancillary features like NAT/PAT translations
- Can be used for point to point encrypted communications like IPSec

# FW Weaknesses

- Can be bypassed by systems with multiple network connections
- e.g. Laptop with wired, wireless and cellular data connections
- Hard to filter certain categories of traffic
- e.g. Inbound & Outbound HTTP/HTTPS
- Can be bypassed by Malware in email, drive-by-downloads, USB drives...

# FW Policies

* Set a default for no policy match
* Allow, Deny, Drop
* Policy is generally a set of rules/ACLs that are run sequentially

# FW Types

- Packet Filtering Firewall
- Makes simple decisions based on src/dest IP, src/dest Port, Protocol (TCP/UDP)
- Also network interface traffic arrives on and some well known ports SSH, SNMP, ...

# FW Types

- Packet Filtering Firewall weaknesses
- Spoofed IP addresses - craft a packet with an internal IP
- Source routing attacks - specify how packet is routed
- Split data into tiny fragments - either make decision on first packet or reassemble

# FW Types

- Stateful Firewalls
- Understands Packet filtering plus the context/state of the communication
- New, Related, Established 
- Tracks the state of communication through it

# FW Types

- Stateful Firewall weaknesses
- State table is of a finite size of RAM
- Fail open or closed when state table is full?  Or maybe just reboot
- More code, more complexity

# FW Types

- Application-layer Firewall
- Stateful plus understanding of a specific application protocol
- e.g. SMTP, HTTP, HTTPS
- "Deep Packet Inspection"[3] - looks at the application specific data to make decisions
- Hard to do at line speed and in real time

# FW Types

- Application-layer Firewalls weaknesses
- Only inspects a simple application protocal
- Can require multiple blinky-light boxes for broad coverage
- Single point of failure for the app being protected

# Local vs Network firewalls

- Cloud, SDN and autoscaling reduce the usefulness of traditional firewalls
- Move FW to the host and control by software (Chef, Puppet, Salt, Ansible, ...)
- Push 'smarts' to the end point since the devices cannot hit web scale
- Containers/Docker only make this worse

# FW + Cloud Computing

![Firewall Fail](http://appseclive.org/images/alex-stamos-AppSecCali.png)[4]

# IPS

- Intrusion Prevention System
- Recent addition to firewalls
- "Add our IPS card"

# IPS

- Watch traffic for attack patterns and actively block access
- Either part of firewall or talks to it
- Set thresholds and responses
- Blackhole IP, block for N minutes, tarpit, ...

# IPS Weaknesses

- Needs to be tuned - out of box config rarely works
- Accuracy vs hassling legit users
- More code, more complexity
- Signature updates 

# Network Attacks

- DNS spoofing
- ARP poisoning
- Man-in-the-middle attack

# DNS spoofing

- DNS - old Internet service to resolve host names to IP addresses
- Replace the static 'host' file in the early Internet
- Not encrypted, usually UDP 
- Can use TCP when data size is greater then 512 bytes like zone transfers

# DNS spoofing

- Attacks which cause a client to receive or cache incorrect DNS information
- Flaws in DNS software allow attacker to inject their data into cache
- Attacker can direct victim to server of their choice
- Phishing, Drive-by-downloads, ...

# ARP poisoning

- aka ARP spoofing, ARP cache poisoning, ARP poison routing
- Requires attacker to be in the 'broadcast domain' of the target
- basic attack is to inject a MAC address of attacker's choice into victim's ARP table

# ARP poisoning

- ARP has no auth, encryption or state
- Most hosts automatically update cache based on ARP traffic received
- EVEN if they didn't ask for that ARP data

# ARP poisoning

- Attacker sends crafted ARP messages to the network segment with the victim
- Victim's ARP table is updated
- Traffic is sent to attacker's computer
- Attacker acts as gateway or a specific host to monitor, modify traffic from victim

# ARP poisoning

![ARP Poisoning](https://upload.wikimedia.org/wikipedia/commons/3/33/ARP_Spoofing.svg)[5]

# Man-in-the-middle attack

- MitM and a bunch of case varieties
- Attacker sits 'between' victim and another host
- Can be done by ARP attacks to become a gateway
- Can be done by answering quicker on the LAN

# MitM

- Defenses
- DNSSEC
- "Smart" switches
- TLS/SSL & Certificate Pinning & HSTS
- Driftnet for Wifi, SSL downgrade attacks aka sslstrip

# Next time

- Intrusion Detection
- DOS - Denial of Service
- and the rest of the network attacks

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
- Look for "Network Security" in the Lecture notes page on the class Canvas site.
 

# References 

- [1] https://en.wikipedia.org/wiki/Network_security
- [2] https://upload.wikimedia.org/wikipedia/commons/5/5b/Firewall.png 
- [3] https://en.wikipedia.org/wiki/Deep_packet_inspection
- [4] http://www.slideshare.net/astamos/appsec-is-eating-security & 
      https://www.youtube.com/watch?v=-1kZMn1RueI
- [5] https://upload.wikimedia.org/wikipedia/commons/3/33/ARP_Spoofing.svg

% Network Security
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Network Security II

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

# This time

- Intrusion Detection
- DOS - Denial of Service
- and the rest of the network attacks

# Intrusion Detection

- Monitoring and analyzing events on a system to provide near or real-time alerts of attempts to violate the security policy.
- Log monitoring, file integrity, process monitoring
- Basically collect data, analyze that data for potential intrusions

# Intruders

- Unauthorized person who gains access to a user's account on the system
- System user who exceeds their level of authorization or misuses their authorization
- e.g. Nurse looking up celebrity medical records that are not their patient
- Unauthorized person who gains root and used elevated privileges to hide their presence

# Hack or Crack

- Historically, Hacker has meant someone who combines excellence, playfulness, cleverness and exploration in performed activities
- Cracker was used for those exploited vulnerabilities in computer systems/networks.
- Nobody really says cracker anymore, its Hacker

# Motivations

- Doing it for the lolz
- Hacktivism
- Criminals
- Insider attacks
- Whitehat, Grayhat, Blackhat

# Types of IDS

- Host-based IDS
- Network-based IDS

# IDS Components

- Sensor(s) - used to collect data such as processes, system calls, logs, packets
- Analyzer(s) - used to sift through collected data looking for an intrusion. Gather evidence for future use.
- Console/UI - Web or other UI to allow security analysts to review security events and act accordingly

# Why IDS?

- Detect attacks quickly enough to stop or limit damage
- Collects metrics on active attacks seen and verifies effectiveness of security policy
- Can act as a deterrent if its presence is known or discoverable

# Problems with IDS

- False positives
- Alert on an activity that is not a policy violation
- False negatives
- Fail to alert on policy violations
- Balancing act between the two extremes

# Problems with IDS

- Cannot be fully automated, requires tuning and a human brain monitoring its alerts
- Modified as security policies change to keep them in harmony
- Minimal system resource impact plus maximum scale are difficult to achieve
- Alert floods

# Host-based IDS

- Monitor an individual system to
- Log suspicious events
- Send alerts
- Possibly stop active attacks

# HIDS

- Detection by
- Signature detection
- Anomaly detection

# HIDS

- Signature detection
- Use pre-defined attack patterns to match against collected data
- Blind to new or slightly different attacks - the AV problem

# HIDS

- Anomaly detection
- Thresholds - define a frequency that triggers an alert
- Profile based - profile normal usage and detect changes from the 'normal'
- Profiles are hard to get right e.g. monthly metrics gathering 

# HIDS

- Sometime includes file integrity monitoring
- Take a hash of important files and check hashes to detect changes to files
- Alert on changes
- Polling interval can be defeated by malware

# HIDS

- Most have a 'mothership' or central console that aggregate multiple systems
- Must normalize data before sending it on - Win vs Lin events
- Analysis may happen at edge or center

# Network-based IDS

- NIDS
- Monitor 1+ points of a network to detect unusual or malicious traffic
- Network view of attack patterns vs host view
- May store packets for future investigation

# NIDS - Types

- Inline Sensor
- Sits physically between two network segments where all traffic MUST pass through it
- Passive Sensor
- Sits off the network and reviews copies of network traffic

# NIDS

- Which type is more common?
- Passive Sensor

# Passive IDS

![Passive IDS](http://appseclive.org/images/IDS.jpg)[1]

# NIDS

- How to get copies of packets?
- Taps - physical devices which copy packets to two interfaces
- "Mirror"/"SPAN" port on a switch
- A network hub - yeck and out of date

# NIDS Detection

- Recon and attacks
- Port scans, Recursive DNS queries, repeated auth attempts
- Packet Fragmentation, Syn Floods, Spoofed packets, ARP attacks
- DOS and Worm activity
- Command and Control (CnC)

# NIDS 

- Log alerts usually to a central console for review/action
- Start packet capture/save packet capture
- Send TCP resets
- Block IP(s) at firewall - perm or temporary
- Send to honeypot

# Honeypot

- Decoy host/network with extensive monitoring
- Diverts attacker away from real systems
- Collect attacker actions/exploits
- Use "dark IP space" for Honeypots [2]

# Denial of Service

- Direct attack on A of CIA
- DOS / DDOS
- Consume or overwhelm system resources to the point of non-function

#  DOS

- Resources to attack
- Network / bandwidth
- System resources - overload system
- Application resources - e.g. consume all JVM resources

# DOS

- Simply send more traffic than bandwidth - flooding
- Spoof packets with victim as the source IP
- e.g. Ping with victim IP as source
- Trigger a bug in the network stack to cause a crash/segfault

# DDOS

- Use multiple hosts to all focus DOS attacks at a victim
- Usually uses previously compromised computers
- Each host may only use 'normal' bandwidth

# App DOS

- Use application flaws to consume all OS RAM/CPU resources for that app
- Typically only take a small number of request - 1 or more
- Many times appear to legit traffic 
- e.g. Slowloris + nearly complete HTTP & range header

# Network Attacks

- VLAN Hopping
- Smurf Attack

# VLAN Hopping

- VLAN - Virtual LAN
- Uses tagging to group hosts into logical collections
- VLAN hosts do not have use the same switch
- e.g. Isolation is virtual and controlled by network switches not physical connections

# VLAN Hopping

- Attacker pretends to be a switch and 'speaks' VLAN tagging and routing protocols
- Allows attacker same access as a switch - can see multiple VLANs

# VLAN Hopping

- Double tagging
- Attacker puts two tags for external VLANs on packets
- Switch sends to first tag VLAN since attacker isn't on that network
- This VLAN sees the second tag and forwards to second VLAN network

# Smurf Attack

- DDOS attack using the IP broadcast address
- Attacker sends tons of ICMP packet with victim's IP as source to broadcast address
- Hosts on that network segment reply to the victim's IP 
- Multiplies each ICMP packet by the number of hosts on that network segment

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

- [1] https://ia.signal.army.mil/IAF/images/IDS.jpg
- [2] http://www.team-cymru.org/darknet.html

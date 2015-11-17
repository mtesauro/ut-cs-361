% OS & Virt. Security
% Matt Tesauro
% CS 361 - Intro to Computer Security

# OS Security

- Definition:
- The planning, implementation and maintenance of systems which are hardened against attack based on policy.
- Sometimes called vulnerability management
- Ideally based on a risk-assessment

# OS Sec Planning

- Consider...
- Purpose of the system, data stored and services provided
- Categories of users, their privileges and data they will access
- Authentication of users - what method?

# OS Sec Planning

- Consider...
- Management of data stored on the system
- Systems access to other data sources e.g. file servers, NAS, DBs, ...
- Administration of the system - by whom and remote vs local access
- Ancillary security issues - local firewall, logging, anti-virus, regulations, ...

# System Hardening

- Install and patch OS
- Initial install should be as minimal as feasible
- Bios security - boot order, boot passwords, boot devices
- Initial and ongoing OS patching

# System Hardening

- Remove unnecessary services, apps, protocols
- Reduct the overall attack surface
- Remove services + local firewall for only required ports
- IPv6 - remove if not needed 
- SSH protocol 2 only

# System Hardening

- Setup users, groups and authentication
- Which users need what permissions, least privilege
- Is Mandatory Access Control (MAC) required? 
- Group setup and population can be critical
- Change or remove default user accounts
- Auth-n - Single sign-on, local users, password policies

# System Hardening

- Constraining resources
- Set max limits on various system resources
- Max process, max RAM per process, max open files, ...
- System vs application constraints

# System Hardening

- Additional measures
- Anti-virus software, OS & uploads
- Host based firewall
- HIDS and file integrity checks
- Centralized log server(s)
- Whitelist applications

# System Hardening

- Once you've hardened the system,
- what's next?
- Test to verify your systems attack surface
- Scan vs agent

# Hardening apps

- For apps that are the reason for the server,
- Create a specific user and directory structure for the service
- Remove test data, default users, default passwords/tokens, etc
- Run app as that app's user with limited privileges
- HIDS on app files, limit resources aka JVM memory

# Operational Security

- On going maintenance of the system during operations
- Helps maintain security posture in a changing landscape
- The basic blocking and tackling of Info Sec

# Op Sec

- Monitoring and analyzing logs
- Setup and perform regular backups
- Recovering from security compromises
- Regular security testing
- Software updates

# Op Sec

- Logging is fundamental
- FTC Startup Security - "never throw away any logs"
- Critical for anomaly detection for security, performance, availability
- Remote logging protects against local compromises

# Op Sec

- Collecting logs
- Security Information Managers (SIM) 
- Security Information and Event Management (SIEM)
- Free things like Elastic Search, LogStash, Kibana, ...
- Gather, analyze, alert humans based on thresholds 

# Op Sec

- Regular backups
- Weekly, daily, hourly & full vs incremental
- Do them and make sure restores work
- Recovering from security compromises
- Can you trust an pwn3d system?

# Op Sec

- Regular testing
- Check list, policy and/or regulatory driven
- Automated vs manual
- Internal vs 3rd party
- Credentials vs non-credentials
- Scanner vs agent 

# At the end of the day...

- Make sure your effort is not greater
- then the potential damage

# The right balance [2]

![Too Safe?](http://whatabikecando.com/wp-content/uploads/2011/04/Too-Many-Bike-Locks.jpg)

# Virtualization Security

- Virtualization allows for multiple OSes to share the same physical hardware
- Beyond OS security, virtualization creates unique security considerations

# Virtualization types

- Full Virtualization
- Nearly total simulation of actual hardware by the hypervisor
- Paravirtualization
- Guest OSes run in isolated domains instead of simulating hardware
- Guest OSes need to be modified to work under Paravirtualization

# Virtualization [3] 

![Example Virtualization](https://lelunha.files.wordpress.com/2012/07/comparision-intel-architecture-and-vmware-esx-server3.png)

# Containers [4] 

![Container vs VM](https://insights.sei.cmu.edu/assets/content/VM-Diagram.png)

# Containers + Google 

- 'Everything' at Google runs in containers
- Start more then 2 billion containers per week [5]
- That's ~3,300 containers every second of every day
- 17,820,000 during this class

# Virt Sec Issues

- All the OS Security issues we've already talked about

# Virt Sec Issues

- Guest OS Isolation
- Ensuring that a guest OS cannot interact with other guests or the hypervisor
- Includes covert interactions of the guest
- Ultimate attack is guest to hypervisor

# Virt Sec Issues

- Hypervisor access to guests
- Hypervisors monitor and have full access to guests.  
- Guests must trust that hypervisors are secure and admin'ed properly

# Virt Sec Issues

- Management of VM images and backups
- Why own a server when you can get a complete copy?
- Hypervisor-like access required for image-level backups
- Shared images and information disclosure

# Virt Sec Issues

- Many security devices/software don't know how to work when virtualized
- Can't use IPS for hypervisor to hypervisor network traffic - enc tunnel
- Assume physical access that isn't available
- Most don't horizontally scale - especially dynamically
- Modern security is moving to agents running in the VM

# DevOps

- Systems as cattle not pets
- Don't fix a broken system, create a new system
- Especially for horizontally scaling apps

# Pets vs Cattle [6]

![Servers as Cattle](http://image.slidesharecdn.com/petsvscattle-serversevolved-150227100431-conversion-gate01/95/pets-versus-cattle-servers-evolved-4-638.jpg?cb=1425031870)


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
- Look for "OS and Virtualization Security" in the Lecture notes page on the class Canvas site.

# References 

- [1] http://csrc.nist.gov/publications/nistpubs/800-123/SP800-123.pdf
- [2] http://whatabikecando.com/holy-krypto-holder-batman/
- [3] https://lelunha.wordpress.com/2012/07/19/140/
- [4] https://insights.sei.cmu.edu/devops/2015/01/devops-and-docker.html
- [5] http://www.theregister.co.uk/2014/05/23/google_containerization_two_billion/
      https://speakerdeck.com/jbeda/containers-at-scale
- [6] http://www.slideshare.net/phil.cryer/pets-versus-cattle-servers-evolved-45229228

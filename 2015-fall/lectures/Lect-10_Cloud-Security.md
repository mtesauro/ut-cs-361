% Cloud Security
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Cloud Security

- NIST Definition:
- A model for enabling ubiquitous, convenient, on-demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services) that can be rapidly provisioned and released with minimal management effort or service provider interaction. This cloud model promotes availability and is composed of five essential characteristics, three service models, and four deployment models. [1]

# Characteristics 

- Broad network access
- Using the service is available over the network usually through REST APIs or client programs
- Rapid Elasticity
- Ability to expand/reduce the use of the service/resource dynamically

# Characteristics 

- Metered/Measured service
- Measured billed based on usage is small time increments e.g. cost/minute, cost/GB transfered...
- On-demand self-service
- User's provision service without any human interaction.  Same for de-provision

# Characteristics

- Resource pooling
- Larger or multiple physical hardware is gathered to provide resources to subdivide between customers
- Customer requests are from this larger pool and broad controls may be available (data center, region, etc) 
- Customers have no say on exactly where their resources run - e.g. that server

# Service Models

- Software as a service (SaaS) 
- On-demand software where application access is provided on a per-user or subscription basis.  
- Provider runs everything from the application down to hardware

# Service Models

- Platform as a service (PaaS) 
- Provides an environment to run customer apps written in 1+ computer language
- Some provide ancillary services such as database, load-balancing, etc.
- Provider runs everything from the programming environment down to hardware

# Service Models

- Infrastructure as a service (IaaS)
- Provides access to processing, storage, network or other computer resources
- Customers run arbitrary software, OSes or store data using this service
- Provider runs the virtualization software and the hardware powering it

# Service Models

- Container as a service (CaaS)
- Provides a platform to run OS containers such as Docker, LXC
- Customer runs arbitrary code and OS software on a shared kernel
- Provider runs the container software, OS and the hardware powering it

# Service Models

![Service Models](https://upload.wikimedia.org/wikipedia/commons/3/3c/Cloud_computing_layers.png)

# Deployment

- Public cloud
- Cloud service is available to any member of the public or members of group
- Provider controls both infrastructure and cloud service
- Amazon, Public GitHub, Rackspace, Heroku, ...

# Deployment

- Private cloud
- Cloud deployment for a single organization for its internal use
- Infrastructure may be on premise or off premise (your data center or not)
- Provider is responsible for the infrastructure only (in come cases)

# Deployment

- Hybrid cloud
- 2+ cloud deployments which mix public and private clouds
- Allows for use of both depending on needs/requirements
- e.g. Run on private cloud, burst out to public cloud for peak usage
- e.g. Private cloud for all but production

# Deployment

- Community cloud
- Infrastructure shared by several organizations with shared goals/concerns
- Managed by community or 3rd party, on prem or off prem

# Problems with Cloud Computing

- All the same as running your own services plus...
- API Security issues
- Auth-N, Auth-Z, DOS and other AppSec issues with the APIs that power a cloud provider

# Problems with Cloud Computing

- Malicious insiders
- Insider attacks at a cloud provider can compromise the security/data of multiple customers
- Shared technology issues
- Since resources are pooled and shared, isolation must be provided by software, hardware, hypervisors
- Failures in isolation allow for cross-customer attacks

# Problems with Cloud Computing

- Data loss / leakage
- Critical company data will be residing on servers not under their direct control
- Account/Service hijacking
- Stolen/exposed credentials or API keys/tokens allow attackers to control the victim's account

# Problems with Cloud Computing

- Unknown risk profile
- Control of a portion of a process is given over to the cloud provider, risk profiles can differ
- Users can purchase/use providers beyond normal business processes - shadow IT

# Isolation issues

- Multi-instance model
- Each customer is provided by a unshared resource constrained by hypervisor
- Multi-tenant model
- Each customer is provided resources separated only by virtual/software separation
- Each tenant's resource is tagged for only that tenant not may not be an exclusive instance of the resource

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
- Look for "Database Security" in the Lecture notes page on the class Canvas site.

# References 

- [1] http://www.nist.gov/itl/csd/cloud-102511.cfm
      http://csrc.nist.gov/publications/PubsSPs.html#800-145
      http://csrc.nist.gov/publications/nistpubs/800-145/SP800-145.pdf


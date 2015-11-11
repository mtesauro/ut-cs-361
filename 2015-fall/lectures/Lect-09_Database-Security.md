% Database and NoSQL Security
% Matt Tesauro
% CS 361 - Intro to Computer Security

# Database Security 

- Defined
- concerns the use of a broad range of information security controls to protect databases 
- including the data, the database applications or stored functions, the database systems, the database servers and the associated network links
- Wikipedia [1]

# Network Security

- Defined #2
- Maintain the CIA triad of a database / data store

# Why are databases targeted?

- Its the data
- Its concentrated in one central place
- Many systems need to connect to databases

# Bits of a database

- System tables - holds description of the DBs and their attributes for the system
- Access and Authorization tables - holds access control data for DB users 
- Database(s) and their physical storage - actual data stored in the DB and how its put on disk

# Admin of DBs

- Centralized - few privileged users grant/revoke access
- Ownership-based - owner/creator of table grant/revoke access
- Decentralized - Ownership + can give users grant/revoke privs

# System vs Object privs

- System privileges
- Admin-type activities in a DB system e.g. create/drop database, procedure, trigger, etc
- Object privileges
- Create, insert, delete, update, read, write

# Access controls for DBs

- Discretionary access control
- Role-based access control (RBAC)

# Discretionary

- Same as before, owner/creator determines access
- Usually constrained within the database
- e.g. owner of db1 cannot grant access to db2

# Discretionary

- General categories of users
- Application owner - user who owns the DB as part of a app
- End user - uses the DB but doesn't own DB objects
- Administrator - admins all or part of the DB

# RBAC

- Like before, roles are created with specific rights/access
- Users are given role(s) that control their access

# RBAC

- Role types
- Server roles - used for admin rights aka system privileges
- Database roles - used for user rights aka object privileges
- User-defined roles - database user creates custom rights within scope of their DB
- Not all have user-defined roles

# Server Roles

- root or system admin
- complete control of DB server
- security admin
- manage logins, set Create DB privs, read logs, change passwords
- DB creator, bulk admin, ...

# Database Roles

- owner - all privileges on DB
- access admin - add/remove users to DB
- data reader & data writer - read-only & read-write users in the DB
- security admin, backup admin, ...

# Granularity of Access control

- Database level
- Table level
- Row level
- Cell level
- Depends on vendor, lower levels = more complexity

# Database monitoring

- Like a IDS/IPS for DBs + WAF features (Web Application Firewall)
- monitors access to DB by user, query, data requested, CPU usage...
- determine what is normal and what is not
- inline or agent-based, can block access based on condition(s)

# VM and Audit

- Vulnerability Management
- System hardening and patching, usually to a standard
- Audit
- Logging and reviewing logs for anomalies and confirm compliance

# Inference attacks

- Combining access to multiple data sets to infer sensitive data
- Can use both non-sensitive data and meta-data
- Interview committee example

# Inference example

- Transport hub for the military [2]
- Multiple cargo holds to store goods in transit
- Some goods may be classified
- With clearance, see everything
- Without clearance, see non-classified only

# Full Table [2]

![Full table](https://raw.githubusercontent.com/mtesauro/ut-cs-361/master/2015-fall/lectures/images/inference-01.png)

# Non-cleared view [2]

![Non-cleared view](https://raw.githubusercontent.com/mtesauro/ut-cs-361/master/2015-fall/lectures/images/inference-02.png)

# Database encryption

- Considered a means to protect data in the DB from exposure
- Support is mixed across DB vendors

# Levels of encryption

- Entire DB
- Row level - selected rows encrypted
- Column level - selected columns are encrypted
- Field level - individual fields are encrypted

# Encryption safety

- Database encryption protects against SQL Injection
- True or False?
- False.  Data is decrypted before sending to application

# Problems with DB encryption

- Like all crypto, you have a key to manage
- HSM can help but $$$$$
- Can causes problems for searching/indexing records
- Can still be vulnerable to inference attacks
- Data has to be decrypted at some point...

# DB vs NoSQL

- Same issues - just a different method to store/retrieve data
- However...
- Most NoSQL have MANY fewer security features e.g. no separation at DB level
- Due to immaturity and assumptions of a non-hostile network environment
- Many key/value stores also similar (Redis, etcd, ...)

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

- [1] https://en.wikipedia.org/wiki/Database_security
- [2] http://databases.about.com/od/security/l/aainference.htm 


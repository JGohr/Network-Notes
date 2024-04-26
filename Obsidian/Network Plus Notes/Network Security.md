---

---
---
### CIA Triad
CIA Triad: Confidentiality, Integrity, Availability

Confidentiality: Keeps data private and safe using encryption and authentication methods

Encryption Types:
- Symmetric: Sender and receiver use the same key to encrypt and decrypt a message
	- DES (Data Encryption Standard): A 56 bit encryption key to secure data and considered weak
	- Triple DES: Uses three different 56 bit keys (ENC -> DEC -> ENC)
	- AES (Advanced Encryption Standard): 128but, 192-bit and 256-bit symmetric encryption method
	- Symmetric is almost 1000x faster than asymmetric encryption
	- Key management is the hardest factor for symmetric encryption
- Asymmetric Encryption: Sender and receiver use different keys
	- PKI (Public Key Exchange): Gives secure email exchanges and web browsing and solves the problem of having to distribute the keys ahead of time
	- Asymmetric uses public and private keys
	- Public Key = Digital Certificate

Integrity: Ensures data was not modified in transit and verifies it came from the original source

MD5 = 128-bit hash
SHA-256 = 256-bit hash
CRAM-MD5 = Md5 variant used in email systems

Availability: Measures data accessibility and is increased by designing redundant networks

---

### Threats and Vulnerabilities

Threat: A person or event that has the potential to for impacting your network
	Internal Threat: Any threat that originates within the org itself
	External Threat: Any threat that could be hacker, weather, activist, etc.

Vulnerability: A weakness in your system that could result in poor outcomes
- Environmental: Undesirable conditions or weaknesses that are around the area of the network
- Physical: In the building or network room
- Operational: Focused on how the network is being administrated with policies/procedures
- Technical: System specific conditions that create security weakness
	- CVE (Common Vulnerability Exposure): A list of publicly disclosed weaknesses
	- Zero-day: Any weaknesses that is unknown when the system is created/implemented
- Exploit: Piece of code that takes advantage of a security flaw

### Risk Management

Function: The identification, evaluation and prioritization of risks to minimize, monitor and control the vulnerability exploited by a threat.

Risk Assessment: A process that identifies potential hazards and analyzes what could happen if a hazard occurs
- Security: Implement Key Security Controls
- Threat: Identifying threats that may be used to attack the system/network

MITRE ATTACK: DB of known attacks

Vulnerability Assessment: Identifying vulnerabilities in a network and planning a resolution, tools to find this are:
- NESSUS
- QUALYSGUARD
- OPENVAS

Pen Test: Trying to safely exploit a system by exploiting vulnerabilities

Posture Assessment: Seeks threats caused by misconfiguration and patching delays

Business Risk Assessment:
- Process: Is your organization conducting properly from a security standpoint
- Vendor: Reducing the risk of supply chain incidents (Cisco counterfeit switch example)

### Security Principles

Least Privilege: Using the minimum level of permission to complete a task 

Role Based Access: 
- DAC (Direction Access Control): Access is determined by owner of the resource
- MAC (Mandatory Access Control): Computer System gets to decide who can access what objects using data labels
- RBAC: Controller by the system but has a set of permissions instead of individual permissions, could be grouped by department

Zero-trust: Requires users to authorized and authenticated before being able to access any data

### Defense In-Depth

Function: Approach in cyber security that layers certain practices to ensure security

DMZ: Perimeter network that protects an orgs internal LAN from untrusted traffic, protects public facing services

Screen Subnet: Subnet in the network architecture that uses a single firewall with three interfaces to connect three dissimilar networks
- Triple homed firewall

Separation of Duties: Prevents frauds and abuse by distributing various tasks and approval authorities across a number of different users

Dual Control: Two people have to be present to perform a action

Split Knowledge: Splitting the knowledge between two people

Honeypot: Attract and traps potential attackers to counteract any attempts at unauthorized access to a network

### Multi-factor Authentication (MFA)

Function of MFA Authenticates an identity with more than one method

| Authentication     | AKA       | Examples                      |
| ------------------ | --------- | ----------------------------- |
| Something you know | Knowledge | Usernames, PINs, Passwords    |
| Something you have | Possesion | Smartcards, RSA Key, RFID Tag |
| Something you are  | Inherence | Fingerprints, Retina Scan     |
| Something you do   | Action    | How you sign your name        |
| Somewhere you are  | Location  | Geotagging/fencing            |

Dictionary Attack: Guesses the password by attempting to check every single word or phrase within a word list

### Authentication Methods

Lightweight Directory Access Protocol :
- LDAP Port 389 / Secure Port 636
- Validates a username and password combination against an LDAP server as a form of authentication

Active Directory: Organizes and manages everything on the network including clients, servers, devices and users.

Kerberos: Focused on authentication and authorization within a windows domain environment
- Provides secure authentication over a insecure network

Single Sign On (SSO): Establishes a default user profile and assigns resources to that user 

### Network Access Protocols

Remote Authentication Dial-In User Service (RADIUS): Provides centralized administration of dial-up, VPN and wireless network authentication
- Authentication, Authorization, Accounting
- Port 1812/1645 Authentication Messages
- Port 1813/1646 Accounting Messages
- UDP 

Terminal Access Controller Access Control System Plus (TACACS+): Used to perform the role of an authenticator in an 802.1x network
- TCP
- Port 49
- Great for Cisco devices

802.1x: A standardized framework that's used for port-based authentication on both wired and wireless networks
- Supplicant (User), Authenticator (Switch, WAP), Authentication Server (RADIUS or TAC Server)

Extensible Authentication Protocol (EAP): Allows for numerous different mechanisms of authentication
- EAP-MD5: Utilizes simple passwords and the challenge handshake authentication process to provide remote access authentication
- EAP-TLS: Uses public key infrastructure with a digital certificate being installed on both the client and the server
- EAP-TTLS: Requires a digital certificate on the server and a password on the client for its authentication
- EAP Flexible Authentication via Secure Tunneling (EAP-FAST): Uses a protected access credential to establish mutual authentication between devices
- Protected EAP (PEAP): Uses server certificates and Microsoft Active Directory databases to authenticate a clients password
- Lightweight EAP (LEAP): A proprietary protocol that only works on Cisco-based devices

### Network Access Control

Function of NAC: Ensures a device is scanned to determine its current state of security prior to being allowed network access

Persistent Agent: A piece of software installed on a device requesting access to the network
Non-Persistent Agent: Requires the users to connect to the network an go to a web based captive portal to download an agent onto their devices

IEEE 802.1x: Used in port based network access control
- Time based: Defines access periods for given hosts on using a time based schedule
- Location based: Evaluates the location of the endpoint requesting access using IP or GPS geolocation
- Role based (Adaptive NAC): Reevaluates a device's authentication when it's being used to do something
- Rule: Uses a complex admission policy that might enforce a series of rules with the use of logical statements

### Physical Security

Infrared Camera: Heat based detection

Ultrasonic Camera: Sound based detection

Asset Tag: Identifies a piece of equipment using a serial number/barcode

Tamper Detection: Ensures a network has not been modified/tampered with

eFuse: Electronic detection mechanism that can record the version of the IOS used by the switch

Access Control Vestibule (Mantrap): An area between two doorways that holds people until they are identified and authenticated

Smart Locker: A fully integrated system that allows you to keep your laptop or other valuables inside

### Asset Disposal

Function: Disposing of a system whenever it is not longer need

Degaussing: Exposing a hard drive to a magnetic field to clear data

Purging: Special techniques to wipe the data from a drive that cant be reconstructed

Clearing Technique: Removes data with a certain amount of assurance that it cant be reconstructed

Data Remnants: Leftover pieces of data that may exist in the hard drive we no longer need


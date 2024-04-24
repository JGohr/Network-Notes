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

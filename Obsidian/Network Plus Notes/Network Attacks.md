#### Denial Of Service Attacks (DDOS)
Occurs when one machine is flooding a victim with requests for service

TCP (SYN Flood): Occurs when a attacker initiates multiple TCP sessions, but never completes
Smurf Attack (ICMP Flood): Occurs when an attacker sends a ping to a subnet broadcast address with the source IP spoofed to be that of the victim server

Distributed Denial of Service Attack: Occurs when an attacker uses multiple computers to ask for access to the same server at the same time

Botnet: A collection of compromised computers
Zombie: A single compromised computer
#### General Network Attacks

On-Path Attack or MITM attack: Occurs when an attacker puts themselves between the victim and the intended destination

Session Hijacking: Occurs when an attackers guesses the session ID that is in use between a client and a server and takes over the authenticated session.

DNS Poisoning: Occurs when an attacker manipulates known vulnerabilities within the DNS to reroute traffic from one site to a fake version of that site

DNSSEC: Uses encrypted digital signatures when passing DNS information between servers to help protect it from poisoning

Rogue DHCP Server: A DHCP server on a network which is not under the administration of yourself/your team
#### Spoofing Attacks

Function of Spoofing: Occurs when an attacker masquerades as someone else

IP Spoofing: Modifying the source address to hide the identify of the attacker

MAC Spoofing: Modifying the MAC address to pretend to use a different NIC card
-  MAC Filtering: Relies on a list of all known and authorized MAC addresses

ARP Spoofing: Sending falsified ARP messages over a LAN

VLAN Hopping: Send traffic from one VLAN to another, bypassing the VLAN segmentation.
- Double Tagging: Connecting to an interface on the switch using access mode with the same VLAN as a native untagged VLAN on the trunk
- Switch Spoofing: Attempting to conduct a Dynamic Trunking Protocol negotiation
#### Malware

Malware: Designed to infiltrate a computer system and possibly damage it

Virus: Malicious code that is run on a machine without users knowledge

Worm: A piece of malicious software that can replicate itself without user action

Trojan Horse: Malicious code that is disguised as harmless software
- RAT (Remote access trojan): Provides the attacker remote control of the client

Ransomware: Restricts a victims computer until ransom is received for control

Spyware: Gathers information without your consent

Root kit: Designed to gain admin controls over a system without being detected

#### Wireless Attacks

Rogue Access Point: Any WAP that has been installed on a network without authorization
- Shadow IT: Use of IT devices without the approval of the IT department

Evil Twin: WAP that uses the same name as your own network

De-authentication: Interrupts communication between a client and a WAP

Password Attack: Uses dictionary attack or brute force attacks to crack your access point

Wireless Interception: Captures wireless data packets as they travel amongst the air

Wi-Fi Protected Setup: Connecting to a wireless network without passwords, instead using Id numbers or other antics.

#### Social Engineering

Phishing: Sending an email in a attempt to get a user to click a link
- Spear Phishing: Targeted form of phishing
- Whaling: Focused on key executives within a company

Tailgating: Enters a secure portion of a org by following a authorized users entry

Piggybacking: Tailgating but with a employees consent

Shoulder surfing: Coming up behind an employee and trying to use direct observation to obtain information

Eavesdropping: Listening on a conversation

Dumpster diving: Seeking personal or confidential info in the trash

#### Insider Threat

Employee or trusted insider who uses their authorized access for malicious activity

Logic Bomb: Type of malware that is tied to a logical event or specific time
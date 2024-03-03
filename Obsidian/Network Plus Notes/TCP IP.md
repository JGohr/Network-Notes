## TCP/IP Overview

Alternative name: DoD Model 

Uses four layers instead of seven, combining the seven OSI layers
    - Application (OSI 5-7)
    - Transport (OSI 4)
    - Internet (OSI 3)
    - Network Interface (OSI 1-2)

TCP/IP: (NI)ITA | OSI: PDNTSPA

Network Interface Layer: How to transmit (bits) across a network and determine how to use the medium

Internet Layer: Where data is taken and packaged into (IP datagrams)

Transport Layer: Defines the level of service and the status of connection being used
    - TCP Connectionful
    - UDP Connectionless
    - RTP Real Time

Application Layer: Dictates how programs are to interface with the transport layer via session mgmt

***
## Data Transfer Over Networks

Port: A 'logical' opening on a system representing a service or app thats listening for traffic
    - 0 -> 65,535
    - Well Known/Reserved: Ports 0 -> 1023
    - Ephemeral Ports: 1024 -> 65,535

IPv4 Packet: Consist of a source address, destination address, IP Flags & Protocol
### Ports & Protocols
Format: Protocol | Port Number | Usage

File Transfer Protocol (FTP) | 20, 21 | Provides insecure file Transfer
Secure Shell (SSH) | 22 | Provides secure remote control of another machine using text env
Secure File Transfer Protocol (SFTP) | 22 | Provides secure file transfers
Telnet | 23 | Provides insecure remote control of antoher machine using a text based env
Simple Mail Transfer Protocol (SMTP) | 25 | Provides the ability to send emails over the network
Domain Name System (DNS) | 53 | Converts domain names to IP addresses and vice versa

Dynamic Host Control Protocol (DHCP) | 67, 68 | Automatically provides networks params to your clients such as: 
    - IP addresses
	- Subnet mask
    - Default gateway
    - Dns server

Trivial File Transfer Protocol (TFTP) | 69 | Used as a lightweight FTP for sending congfig files or PXE booting
Hypertext Transfer Protocol (HTTP) | 80 | Used for insecure web browsing                  
Post Office Protocol Version Three (POP3) | 110 | Used exclusively for inbound email
Network Time Protocol (NTP) | 123 | Used to keep accurate time for clients on a network
Network Basic Input/Output System (NetBIOS) | 139 | Used for file or printer sharing in a WINDOWS network
Internet Mail Application Protocol (IMAP) | 143 | A newer method of retrieving incoming emails which improves POP3
Simple Network Management Protocol (SNMP) | 161, 162 | Used to collect data on/monitor network devices
Lightweight Directory Access Protocol | 389 | Used to provide directory services to your network, like AD
HTTP Secure (HTTPS) | 443 | Used for secure web browsing using SSL or TLS
Server Message Block (SMB) | 445 | Used for windows file and printer sharing services
System Logging Protocol (SysLog) | 514 | Used to send logging dta back to a centralized server
SMTP TLS | 587 | Secure and encrypted way to send emails
LDAPS | 636 | Provides secure directory services
IMAP over SSL | 993 | Secure and encrpyted way to recieve emails
POP3 Over SSL | 995 | Secure and encrypted way to recieve emails
Structured Query Language Server Protocol (SQL) | 1433 | Used to comm from a client to a database engine
SQLnet Protocol | 1521 | Used for comm from a client to an orocale database
MySQL | 3306 | Used for comm from a cleint to the MySQL database engine
Remote Desktop Protocol (RDP) | 3389 | Provides graphical remote control of another client or server
Session Initiation Protocol (SIP) | 5060, 5061 | Used to init VoIP and video calls

### Finding Open Ports

Nmap: Command line tool that maps a network
    Command Args: -sS (Syn Scan for SYN-ACK), -O (Operating System)

ZenMap: Graphical interface for nmap

###  IP Protocol Types

TCP: Conducts a three way handshake between a client and a server while using windowing for optimized traffic | Connection Oriented

UDP: Detects if packets are corrupted when they are recieved using a checksum | Connectionless but faster

Generic Routing Encapsulation (GRE): Creates a tunnel to share data between two devices over a public network | 'No encrpytion'

Internet Control Message Protocol (ICMP): Used to communicate info about network connectivity back to the sender, sends ICMP datagrams | Example: ping command in cmd

IPSec: Used to protect one or more data flows between peers | Provides confidentiality, integrity and authentication on data. A form of tunneling.
    - Lets you encrypt your tunnel
    - Used heavily in VPNS
    This protocol uses two headers:
        - Authentication Header (AH): Protocol within IPSec that provides authentication and integrity on data via hashing
        - Encapsulation Security Payload (ESP): Provides encrpytion and integriy for the data packets sent over IPsec protocol
        - Main difference: ESP uses encrpytion and authentication algorithms while AH uses hashing
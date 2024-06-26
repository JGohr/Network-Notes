## OSI Overview

802.11 WIFI
802.3 Ethernet

Section 2
OSI - Open Systems Interconnection 
ISO 7498 ^ OR OSI Stack
OSI Model is a reference model for all networks

OSI Layers Bottom to Top:
    Physical + Bits
    Data Link + Frames
    Network + Packets
    Transport + Segments
    Session + Data
    Presentation + Data
    Application + Data

PLEASE DO NOT THROW SAUSAGE PIZZA AWAY

DO SOME PEOPLE FEAR BIRTHDAYS (Reversed)
***
## Physical Layer : L1

PHYSICAL LAYER (Layer 1)
    Where transmission of bits across the network occurs and includes physical and electrical network

Transition Modulation: If the incoming signal changes during the clock cycle, then a 1 is represented, other a 0 is presented.
    the transition between voltages or the presence of light indicates a binary value
    Fiber is interpreted as on (1) or off (0)

Layer 1 devices view networks from a physical topology

Synchronization on this layer can be asynchronous or synchronous
    Asynchronous: Uses start and stop bits to indicate when transmission occurs
    Synchronous: Uses a reference clock to coordinate the transmissions by both sender and receiver

Broadband vs Baseband: Broadband separates bandwidth into channels while baseband utilizes all available frequencies on a cable
    Baseband uses a reference clock to utilize synchronous communication
    Base = Single, Broad = Multiple

[[Multiplexing]]: Allows multiple people to use a baseband connection 
    - Time Division Multiplexing(TDM): Each session takes a turn, using time slots, to share the medium between all users
    - StatTDM: Dynamically allocates the time slots on a as needed basis 
    - Frequency Division Multiplexing: Divides the medium into channels based on frequency and each session is transmitted over a different 

Layer 1 Device: [[Hub]]
***
## Data Link Layer : L2
Package bits into frames to transmit over a network
MAC: Media Access Control (Logical) / Uses a 48-bit address which is hexadecimal
First 24bits = vendor code, last 24 = unique id 

LAYER 2 VIEWS DEVICES LOGICALLY
ARP (Address Resolution Protocol)

Logic Link Control 
    Provides connection services
    Allows acknowledgement of receipt of messages 
    Provides flow control
    Provides error control via checksum

Communication Synchronization:
    Isochronous - Uses a common reference clock and creates time slots for transmission of data
    Synchronous - Uses the same reference clock, will use beginning and ended frames to tell when to start and stop transmission
    Asynchronous - Uses individual reference clocks and uses start and stop bits, no control over when devices can communicate 

Types of operations: [[Switch]], MAC Addresses, [[Bridge]]
***
## Network Layer : L3
Forwards traffic with logical address, known as routing

172.16.254.1 - IPv4 Address - Dotted Octet Notation

Ways to route/forward traffic:
    Packet Switching:
        Data is divided into packets and forwarded
        MOST NETWORKS USE PACKET SWITCHING

Circuit Switching: Dedicated communications link is established between two devices

Message Switching: Data is divided into messages which can be stored and forwarded

Route Discovery & Selection (Decision of which path to take to send traffic):
    Routers use a routing table and can statically or dynamically find an IP using techniques such as: RIP, OSPF & EIGRP
    Routing protocols help us decide how traffic is gonna flow and how routers are gonna communicate information

Connection Services (Augment L2 connection services to improve reliability):
        Implements flow control
        Packet reordering: Splits up large amounts of packets and sends them to a specific destination, putting the packets back together at the end. Each packet gets numbered and sequenced
        ICMP: Sends error messages and operational info to IP destination

Devices for L3: [[Router]], [[Multi-layer switch]], IPv4, IPv6, ICMP
***
## Transport Layer : L4

Dividing layer between the upper and lower OSI Stack

PDU = Segments

L4 Protocols: TCP & UDP
     TCP (Transmission control protocol): 
		Connection oriented protocol for reliable transport of Segments
        Seeks acknowledgment for reception of data
	    SYN -> SYN-ACK -> ACK | Three way handshake | C -> S -> C -> S
	        This allows to ensure all data is getting to the destination
            Types of Flags:
                SYN: Used to synchronize connection during three way handshake 
                ACK: Used to acknowledge successful receipt of packets
                FIN: Used to tear down the handshake 
                RST: Used when a client receives a packet that it was not expecting
                PSH: Used to ensure data is given priority
                URG: Labels a packet as urgent, process immediately
                ---P-P--[PSH P P P URG]--P---P--- 
                Header Size: 20 Bytes

UDP (User Datagram Protocol):
    Connectionless protocol that is unreliable way to transport segments
    UDP is for datagrams typically since its unreliable for segments
    If data is dropped sender is unaware
    Really good for audio/video data transfer
    If we used TCP for video and audio buffering would be insane
    Header Size: 8 Bytes

TCP - Reliable, Connection Oriented, Segment retransmission and windowing flow control,
segment sequencing & acknoledgment of segment reception

 UDP - Unreliable, Connectionless, no windowing or retransmission, no sequencing or acknoledgment

Windowing:
    Allows the clients to adjust the amount of data in each segment
    Sends less data with increased retransmissions
     Opening and closing window to optimize bandwith

Buffering:
    Occurs when devices allocate memory to store segments if bandwidth isn't available

    
Layer 4 Devices: TCP, UDP, WAN Accelerators, Load Balancers & [[Firewall]]
***
## Session Layer : L5

Keeps conversations seperate to prevent intermingling of data

Setup, Maintain, Tear down
    Setup: Check user creds and assign numbers to identify
    Maintain: Transfer data across a network, re-establish connection, receipt acknoledgment
    Tear down: Ending session after the transfer is done
Layer 5 Devices:
    H.323 - Used to setup Maintain and tear downn voice and video connections (RTP - Real Time)
    NetBIOS - Used to share files over a network
***
## Presentation Layer : L6

Formats the data to be exchanged and secures the data with encryption

Key Presentation Layer Concepts:
    Data Formatting
    Encryption

Data formatting: Formatting data for compatability between devices
ASCII (American Standard Code for Information Interchange) Ensures data is readable by the recieving system

Encryption is used to scramble the data to ensure its safe upon transfer
TLS (Transport Layer Security) is form of encryption on the 6th layer

Tech for layer 6th: Scripting Languages(HTML, JS), Standard Text, Pictures, Movie files & encryption
    These are all ways of representing data or "presenting" the data

***
## Application Layer : L7

Provides application level services where users communicate
    Types of applications: File Transfer, Network Transfer

Application Services: Unites communicating components from more than one network application
    Types of application services: Email(POP3, IMAP, IMTP, not gmail or outlook), remote access, file transfer, file sharing

Service Advisment: Sending out announcements to other devices on the network to offer services

Types of layer 7 operations: Email applications, web browsing, [[DNS]], FTP, Remote access
    All low level operations

***
## Encapsulation
Encapsulation: The proccess of putting headers/trailers around some data

Each layer of the OSI stack assigns a specific header

PDU - Protocol Data Unit
    A PDU is simply a single unit of information transmitted in a network
    LN PDU is the terminology
    This unit is different depending on the layer its operating on (Bits, Frames, Packets, Datagrams/Segments)

Encapsulation goes down the stack while decapsulation moves up the stack

Payload - the data being sent / PDU

Ethernet minimum payload: 42 bytes using VLAN / 46 Bytes No VLANS

MTU (Maximum transmission unit): Maximum unit size when sending a payload
    If the payload size is larger than 1500, a jumbo frame is required

*** 

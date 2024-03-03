###  Connection Types

Deterministic vs Contention Based:
    - Deterministic: Very organized and orderly, requires electronic token to transmit
    - Contention Based: Very chaotic and can transmit whenever possible
        - Causes collisions
        - Ethernet chose to use contention based networks 
***
### Carrier Sensing & Collision

Carrier Sense Multiple Access w/ Collision Detection (CSMA/CD):
    - Prevents collisions by deferring transmission until no stations are transmitting
    - Carrier Sensing: Listen over the medium for data transmission
    - Upon Collision: Halt transmission and re-transmit after a random backoff timer

Collision Domain: Each area of the network that shares a single segment
    Devices operate in half-duplex mode when connected to a hub
    Keep collision domains small in networks
    Ethernet Switch: Increases scalability of a network by creating multiple collision domains
***
### Fiber Cable Standards:

STANDARD | MODE | BANDWIDTH | DISTANCE
    - 100BASE-FX | MMF | 100 Mbps | 2km
    - 100BASE-SX | MMF | 100Mbps | 300m
    - 1000BASE-SX | MMF | 1000Mbps | 220-550m
    - 1000BASE-LX | SMF/MMF | 1000Mbps | 5km (SMF) or 550m (MMF)
    - 10GBASE-SR | MMF | 10Gbps | 400m
    - 10GBASE-LR | SMF | 10Gbps | 10km

S = Short Distance & MMF 
L = Long Distance & SMF ## BUT ## LX = SMF/MMF 
F = Fast Ethernet over Fiber & MMF
***
### Network Infrastructure Devices

Types of Hubs:
    - Passive: Repeat signal with no amplification
    - Active: Repeats signal with amplification
    - Smart: Active hub enhanced with SNMP (Simple Network Mgmt)

Layer 2:
    - Bridge: Analyzes source MAC addresses and makes smart forwarding choices based on the destination MAC
    - Switch (Multiport Bridge): L2 device that connects multiple network segments together

Layer 3:
    - Router: L3 device that connects multiple networks and makes forwading decisions based on logical net info
    - L3 Switch: Makes L3 routing decisions and then interconnects entire networks, not just segments

DEVICE TYPE | COLLISION DOMAINS | BROADCAST DOMAINS | OSI LAYER
HUB | 1CD | 1BD | OSI 1
BRIDGE| 1CD PER PORT | 1BD | OSI 2
SWITCH | 1CD PER PORT | 1BD | OSI 2
MULTILAYER SWITCH | 1CD PER PORT | 1BD PER PORT | OSI 3+
ROUTER | 1CD PER PORT | 1BD PER PORT | OSI 3+
***
#####  Additional Ethernet Switch Features  #######################

Examples of Ethernet Features:
    - VLANS
    - Trunking
    - Spanning Tree Protocol
    - Link Aggregation (IEEE 802.3ad)
    - POE (Power Over Ethernet)
    - Port Monitoring
    - User Auth

Link Aggregation: Combines multiple physical connections into a single logical connection to minimize congestion
    - IEEE 802.3ad
    - Congestion can occur when ports all operate at the same speed
    - 3 incoming connections at 100Mbps, 1 outgoing connection at 100Mbps, outgoing needs to be 300Mbps
        - We can use remaining outgoing ports to combine them virtually to open up more bandwidth

Power Over Ethernet: 
    - POE (802.3af) / POE+ (802.3at)
    - CAT5 or higher
    - POE provides up to 15.4 watts / POE+ provides up to 25.5 watts
    - PSE (Power Sourcing Devices) / PD (Powered Devices)

Port Monitoring: Makes a copy of all traffic destined for a port and sends it to another port
    - Used for network analysts to monitor traffic

User Auth: Requires users to authenticate themselves before gaining access to the network
    - 802.1x

Management Access and Authentication:
    - Can use: SSH, Console Port (Cable and separate client), Out of band mgmt (Centralized device)
    
First Hop Redundancy: 
    - Uses HSRP (Hot Standby Router Protocol) to create a virtual IP and MAC address to make a active and standby router

MAC Filtering: Permits or denies traffic based on a MAC address
Traffic Filtering: Permits or denies traffic based on a IP address
Quality of Service: Forwards traffics based on priority markings
***
### VLAN & Misc Ethernet Devices
VLAN (Virtual Local Area Network)
    - Allows different logical networks to share the same physical hardware and provides added security and efficiency
    - VLAN Trunking (802.1q): multiple clans transmitted over the same cable
    - VLAN use 4 byte identifier: TPI/TCI (Tag Protocol identifier/Tag control identifier)
	- Untagged VLANs get called "native VLAN" and are labeled 0

Other Ethernet Devices:
	- VoIP Phones: Connects to your IP network to make a connection w/ a call manager on the network
	    - Unified Communications Manager: Call processing for IP phones
	- Physical Access Control Devices: Sec gates, door locks, etc.
	- Security Cam: Separate VLAN connection for security purposes
	- HVAC: Place on own VLAN for proper protections

ICS (Industrial Control System): Describe control systems and instrumentation for industrial networks
SCADA (Supervisory Control and Data Acquisition): Acquire and transmit data from different systems to a centralized point
***
### Spanning Tree Protocol
Spanning Tree Protocol (802.1d) Permits redundant links between switches and prevents looping of network traffic
	- Root Bridge: Switch with the lowest bridge ID (BID)
	- Non-root bridge: All other switches on the topology
	- BID is made up of: Priority value, MAC address
	- Root Port: Every non-root bridge has a single root port which is the closest to the root bridge in terms of cost
		- "Cost": Faster cables = lower cost / Slower cables = higher cost
	- Designated Port: Every network segments has a designated port which is the closest to the root bridge in terms of cost
		- All the ports on the root bridge are designated ports
	- Non Designated Port: Ports that block traffic to create loop free topology
		-Non-designated ports receive bridge protocol data units (BPDUs)

Forwarding State Types:
	- Blocking BPDUs are received but not forwarded
	- Listening Populates the Mac address table but does not forward frames
	- Learning Processes BPDUs and determines switches role in the STP
	- Forwarding Forwards frames for operations	

Shortest Path Bridging: Used instead of STP for larger network environments
Broadcast Storm: Multiple copies of frames being forwarded back and forth which then consumes the network

***
### Specialized Network Devices

VPN Concentrator: Terminates VPN tunnels and allows for multiple VPN connections in one location
	VPN Headend: VPN Concentrator used to terminate IPSec VPN tunnels within a router or other device

Firewall: Network security appliance placed at the boundary of a network
	- Stateful or stateless
	-Software or hardware

NGFW Next Gen Firewall: Conducts deep packet inspection at L7 and can look through traffic to detect and prevent attacks

IDS/IPS: Intrusion (Detection/Prevention) System: Recognizes and responds to attacks through signatures and anomalies

Proxy Server: Makes requests to an external network on behalf of a client

Content Engine/Caching Engine: Performs the caching functions of a proxy server

Load Balancer/Content Switch: Distributes incoming requests across various servers in a server farm








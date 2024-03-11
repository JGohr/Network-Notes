##### IP Address:
Assigned numerical label that is used to identify internet communicating devices on a network
##### Layer 2 vs. Layer 3
Layer 2 works between devices that are internal or on their own LAN
Layer 3 connects those internal networks to communicate at greater distances
##### Standard IP Address Format:
IPv4 (32-bit address) & IPv6 (128-bit address)
***
# IPv4 Addressing

##### IPv4 Presentation:
Dotted Decimal Notation = 192.168.1.1
Each number is known as a "octet" (8bits)
##### Subnet Mask:
Used to distinguish between network bits and host bits
Each octet when converted to binary digits will represent a 1 or 0
1 = Network Bits | 0 = Host bits
Classful Mask = Default subnet mask for a given class of IP addresses

##### IPv4 Classes:
| Class | 1st Octet Value | Default Subnet (Classful Mask) | Possible Hosts  |
| ----- | --------------- | ------------------------------ | --------------- |
| A     | 1 - 127         | 255.0.0.0                      | 265<sup>3</sup> |
| B     | 128 - 191       | 255.255.0.0                    | 265<sup>2</sup> |
| C     | 192 - 223       | 255.255.255.0                  | 256             |
| D     | 224 - 239       | NULL                           | NULL            |
| E     | 240 - 255       | NULL                           | 268M (Reserved) |
Class D is reserved for experimental purposes
Class E is reserved for future use if needed
##### Multicast Address:
A logical identifier for a group of hosts in a computer network
Multicasting = Sending from one source and having multiple people receive it
##### Classless Inter-Domain Routing (CIDR Notation)
Allows for the borrowing of host bits of a subnet and reassigning them to the network portion

**Address Transformation Example:** 255.255.255.0 -> 255.255.255.192
**CIDR Notation:** 192.168.1.4/26
- Number after the slash represents the number of network bits. Since IPv4 addresses utilize 32 bits, we can see how many network bits are being used and know the rest are host bits.

| Class | 1st Octet Value | Default Subnet (Classful Mask) | CIDR Notation |
| ----- | --------------- | ------------------------------ | ------------- |
| A     | 1 - 127         | 255.0.0.0                      | /8            |
| B     | 128 - 191       | 255.255.0.0                    | /16           |
| C     | 192 - 223       | 255.255.255.0                  | /24           |

##### Public (Routable) & Private (Non-routable) IPs
- **Public/Routable IP:** Can be accessed over the internet and is assigned to the network by an ISP
- **Private/Non-routable:** Can be used by anyone at any time, but only within their own local network
- **Network Address Translation:** Allows for routing private IPs through public IPs
- **RFC 1918:** Used to document how organizations could conduct address allocation for private internets (intranets)
- **Internet Corporation for Assigned Names and Numbers (ICANN):** Globally manages and leases publicly routable IP addresses

| Class | Starting Value  | IP Range                      | Possible Hosts |
| ----- | --------------- | ----------------------------- | -------------- |
| A     | 10              | 10.0.0.0 - 10.255.255.255     | /8             |
| B     | 172.16 - 172.31 | 172.16.0.0 - 172.31.255.255   | /16            |
| C     | 192.168         | 192.168.0.0 - 192.168.255.255 | /24            |

##### Specialized IPs
- **Loopback (127.0.0.1):** Creates a loopback to the host and is often used in troubleshooting and testing network protocols on a system. Could also be known as "localhost"
- **APIPA (Automatic Private IP Addresses):** Used when a device does not have a static IP address or cannot reach a DHCP server. 
	- Ranges from 169.254.0.0 -> 169.254.255.255
	- DORA (Discover, Offer, Request, Acknowledge) was a technique previously used by DHCP before APIPA was created
	- Remember if you see 169.254.X.X there is a DHCP problem

##### Virtual IP Addresses (VIP or VIPA):
An IP address that does not correlate to an actual physical network interface.
- Used for: NAT, Fault Tolerance & Virtualization
- Routers often use virtual IP addresses to provide redundancy in their connectivity options
##### Subinterfaces:
A virtual interface that is created by dividing up one physical interface into multiple logical interfaces
#### IPv4 Data Flows
- Unicast: Data travels from a single source device to a single destination device
- Multicast: Data travels from a single source device to multiple (but specific) devices
- Broadcast: Data travels from a single source to all devices on a destination network
***
# Assigning IP Addresses

Types of address assignment: **Static** & **Dynamic**
##### Static Assignment
Manually typing in the IP address for the host, its subnet mask, default gateway & DNS server. This method is very impractical for larger, enterprise networks.
##### Dynamic Assignment
Dynamic allocation of IP addresses and associated addresses. Most SOHO (Small owner/Home Office) devices already run a DHCP server and is turned on by default.
###### Types of dynamic assignment: 
- **BOOTP (Bootstrap protocol):** Dynamically assigns IP addresses and allows a workstation to load a copy of their boot image over a network  
- **[[DHCP]]:** Assigns an IP based on a assignable scope or pool of addresses and provides the ability to configure numerous other options within it. Each IP is leased for a period of time and returns to the pool when the lease is expired.
- **APIPA:** Used when a device does not have a static IP address or cannot reach a DHCP server. APIPA assigned devices cannot communicate outside the LAN or with non-APIPA devices.
- **ZeroConf:** A newer technology based on APIPA which provides a lot of the same features and some new ones
##### Components of a fully configured client:
- IP Address
- Subnet Mask
- Default Gateway
- Server Address (DNS or WINS)

**Windows Internet Name Service (WINS):** Identifies NetBIOS systems on a TCP/IP network and converts those NetBIOS names to IP addresses
***
# Subnetting 

##### Subnetting:
Taking a large network and splitting it up into smaller networks, this is simply done by taking host bits and dedicating them for extra network bits

Borrowing of network bits visualized:
	192.168.32.5 - 255.255.255.0 (11111111.11111111.11111111.00000000)
	to
	192.168.32.5 - 255.255.254.0 (11111111.11111111.11111110.00000000)

[[Subnet]] masks modify subnets and create better scoped networks
Classless subnets range from /25 - /30

Created subnets = 2<sup>s</sup>  (s = number of borrowed bits)

Assignable IP addresses/per subnet = 2<sup>h</sup> - 2 (h = number of host bits)
The -2 in this formula is to compensate for two mandatory addresses in every network: Network ID (First IP in the network) & Broadcast ID(Last IP in the network)

**CIDR Notation:** 192.168.1.4/26
- Shorthand notation used to summarize continuous networks called using route aggregation

**Variable Length Subnet Mask:**
Allows subnets of various sizes to be used and requires a routing protocol that supports it
- Essentially subnetting of subnets

| CIDR | Subnets | Assignable IPs |
| ---- | ------- | -------------- |
| /24  | 1       | 256 - 2        |
| /25  | 2       | 128 - 2        |
| /26  | 4       | 64 - 2         |
| /27  | 8       | 32 - 2         |
| /28  | 16      | 16 - 2         |
| /29  | 32      | 8 - 2          |
| /30  | 64      | 4 - 2          |

##### PAY ATTENTION ON TEST DAY FOR ASSIGNABLE IPS VS TOTAL IPS

***
# IPv6 Addressing

**Address Exhaustion:** Running out of network addresses with IPv4

IPv6 uses 128-bit addresses instead of 32-bits
Hexadecimal: 2018::4815:54AE (:: represents zeros)

IPv6 Benefits:
- Larger address space
- No broadcasts
- No fragmentation / No MTUs
- Can coexist with IPv4
- Simplified Header

Dual Stack Devices: Running IPv4 and IPv6 protocols simultaneously
Tunneling: Allows existing IPv4 router to carry IPv6 traffic
##### Unicast, Multicast & Anycast (Data Flows)

**Unicast:** Used to identify a single interface
- **Globally Routed Address:** Starts with **2000 - 3999**
- **Linked-Local Address:** Begins with **FE80**, like a private IPv4 IP that can only be used on LAN
- **SLAAC (Stateless Address Autoconfiguration):** Eliminates the need to obtain addresses or configuration information from a centralized server
	- EUI (Extended Unique Identifier): Allows a host to assign itself a unique 64-bit IPv6 interface identifier called a EUI-64
	- EUI64 = First 24 bits of the interfaces MAC + FF FE + Last 24 bits of the interfaces MAC
	- This EUI64 will be assigned to the end of the IPv6 first 64 bits to created a globally routed address
- **DHCPv6:** Allows DHCP to auto assign addresses from a DHCPv6 server

**Multicast:** Used to identify a set of interfaces, begins with **FF**
**Anycast:** Assigns a identical address to multiple devices and send data to the nearest/optimal device

**NDP (Neighbor Discovery Protocol):** 
Provides services such as: Router solicitation/advertisement & Neighbor solicitation/advisement + redirection
***



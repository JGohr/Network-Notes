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


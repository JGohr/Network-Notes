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
| Class | 1st Octet Value | Default Subnet | Possible Hosts  |
| ----- | --------------- | -------------- | --------------- |
| A     | 1 - 127         | 255.0.0.0      | 265<sup>3</sup> |
| B     | 128 - 191       | 255.255.0.0    | 265<sup>2</sup> |
| C     | 192 - 223       | 255.255.255.0  | 256             |
| D     | 224 - 239       | NULL           | NULL            |
| E     | 240 - 255       | NULL           | 268M (Reserved) |
Class D is reserved for experimental purposes
Class E is reserved for future use if needed
##### Multicast Address:
A logical identifier for a group of hosts in a computer network
Multicasting = Sending from one source and having multiple people receive it
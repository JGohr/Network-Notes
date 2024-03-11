**Function of a subnet**: Dividing a larger IP network into smaller, more manageable sub-networks or "subnets".

Subnetting is the act of optimal IP address allocation based on a networks needs. This will allow certain subnets to use the same address prefix with differentiating ending octets, depending on the amount of subnets configured.
***

##### Borrowing of network bits visualized:
192.168.32.5 - 255.255.255.0 (11111111.11111111.11111111.00000000)
**to**
192.168.32.5 - 255.255.254.0 (11111111.11111111.11111110.00000000)

By taking the last 1 in the network portion, we modify the third octet into a smaller value. This creates a logical sub network within the address space AND allows for more hosts since we are gaining one extra bit

##### Math for subnetting:
Created subnets = 2<sup>s</sup>  (s = number of borrowed bits)

Assignable IP addresses/per subnet = 2<sup>h</sup> - 2 (h = number of host bits)
The -2 in this formula is to compensate for two mandatory addresses in every network: Network ID (First IP in the network) & Broadcast ID(Last IP in the network)

***
Confused on VLAN vs Subnet? Visit: [[VLAN vs Subnet]]

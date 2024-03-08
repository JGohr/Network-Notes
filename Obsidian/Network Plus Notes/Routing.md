**Function of a router:** Forward traffic between subnets, internal and external networks
Each subnet or external network is going to be its own broadcast domain
#### Routing Tables
Function of a [[Routing Table]]: Helps determine which route entry is the best for for the network by associating IP addresses with MAC addresses.

Route entries with longer prefixes are more specific:
- 125.0.0.0 is less specific than 161.5.0.0
##### Types of routes
**Directly Connected Route:** Physical connections between routers by a serial connection
- Connection drawn as a zig zag line in diagrams
**Static Route:** Manually configured by a administrator
- Default Static Route: 0.0.0.0/0
**Dynamic Routing:** Exchanging information between routers

**Routing Loop Prevention Tactics:**
- Split Horizon: Prevents a route learned on one interface from being advertised out the same interface
- Poison Reverse: Making the route learned on a interface high in cost so the device wont attempt to re-take that route

***
#### Routing Protocols
##### Function of a routing protocol: Decides how to distribute info between routing devices

##### Interior vs Exterior Protocols
Interior Gateway Protocols (IGP): Operate within a autonomous system
Exterior Gateway Protocols (EGP): Operate between autonomous systems

Convergence: Time it takes for routers to update their routing tables in response to a topology change
- Converged Network: When all routers are aware of each table in the network
- Hold down timer: Sets a specific time period to update tables to reduce amount of updates which increases convergence speed
- Hop count: Number of devices it takes to reach final destination

Router Advertisement Methods:
- Distance Vector: Sends full copy of routing table to its directly-connected neighbors at regular intervals, hop focused method
- Link State: Requires all routers to know about all paths of other routers, speed focused method
- Hybrid

Interior Protocols:
- Routing Information Protocol (RIP): Distance vector protocol that uses hop count (maximum count of 15; 16 is infinite)
- Open Shortest Path First (OSPF): Link state protocol that uses cost
- Intermediate System to Intermediate System: Link state protocol that also uses cost and function like OSPF, not widely popular
- Enhanced Interior Gateway Routing Protocol (EIGRP): Hybrid of distance vector and link state protocols that uses bandwidth and delay

Exterior Protocols:
- Border Gateway Protocol: (BGP): Path vector that uses the number of autonomous system hops instead of router hops. BGP will route data through another WAN link if redundant WAN links are available.

Classless Protocols: Protocols that include the subnet mask information when the routing tables or updates are exchanged

Route Believability: Packets decide what protocol is best based on administrative distance. Direct and static connections are most believable then it goes on to other protocols listed above.

Route Redistribution: Allows a network to support more than one routing protocol simultaneously by assign different protocols to different interfaces

Lower metrics are always better in terms of routing

| Routing Protocol                                   | Type                     | Interior/Exterior |
| -------------------------------------------------- | ------------------------ | ----------------- |
| Routing Information Protocol (RIP)                 | Distance Vector          | Interior          |
| Open Shortest Path First (OSPF)                    | Link state               | Interior          |
| Enhance Interior Gateway Routing Protocol (EIGRP)  | Advanced distance vector | Interior          |
| Intermediate System to Intermediate System (IS-IS) | Link State               | Interior          |
| Border Gateway Protocol (BGP)                      | Path Vector              | Exterior          |
***
#### Address Translation

Network Address Translation (NAT): Used to conserve a limited supply of IPv4 addresses by translating private IPs to public
- Dynamic NAT (DNAT): Auto assigns an IP address from a pool and gives 1-to-1 translation
- Static NAT (SNAT): Manually assigns an IP address and gives a 1-to-1 translation
- Port Address Translation (PAT):  Sharing of one public IP by multiple private IP addresses which gives a many-to-one translation

DNAT/SNAT will strip the first three octets of a private IP and assign it them as the first three of the inside global address
- 10.0.0.101 -> 78.56.1.101
PAT will keep track of the request using ports without assigning different IPs
- 10.0.0.101:4100 (Client) / 78.56.1.4 (Inside Global) -> 78.56.1.4:4100

| Address Name   | Use Case                                      | Example Device                |
| -------------- | --------------------------------------------- | ----------------------------- |
| Inside Local   | Private IP address referencing inside device  | Private interface of a client |
| Inside Global  | Public IP address referencing inside device   | Public interface of a router  |
| Outside Global | Public IP address referencing outside device  | Server                        |
| Outside Local  | Private IP address referencing outside device | Private interface of a router |
***
#### Multicast Routing

**Function:** When you send traffic to a class D IP address, known as the multicast group

Internet Group Management Protocol (IGMP): Lets routers known which interfaces have multicast receivers and allows clients to join a multicast group

Protocol Independent Multicast (PIM): Routes multicast traffic between routers and forms a multicast distribution tree
- PIM Dense Mode: Uses periodic flood and prune behavior to form optimal distribution tree. Sends packets across all paths and prunes(removes) all non-optimal routes.
- PIM Sparse Mode: Uses a shared distribution tree and creates and optimal distribution tree through shortest path tree (SPT) switchover. 


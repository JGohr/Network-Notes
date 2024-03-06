Function of a router: Forward traffic between subnets, internal and external networks

Each subnet or external network is going to be its own broadcast domain
##### Routing Tables

Function of a routing table: Helps determine which route entry is the best for for the network by associating IP addresses with MAC addresses.

Route entries with longer prefixes are more specific:
- 125.0.0.0 is less specific than 161.5.0.0
##### Types of routes
**Directly Connected Route:** Physical connections between routers by a serial connection
**Static Route:** Manually configured by a administrator
- Default Static Route: 0.0.0.0/0
**Dynamic Routing:** Exchanging information between routers

**Routing Loop Prevention Tactics:**
- Split Horizon: Prevents a route learned on one interface from being advertised out the same interface
- Poison Reverse: Making the route learned on a interface high in cost so the device wont attempt to re-take that route
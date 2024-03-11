**Function of routing table:** A routing table is a table or database that stores the location of routers based on their IP addresses. This table acts as an address map to various networks.

***
##### Visualizing a routing table

| Network Destination | Netmask       | Gateway  | Interface | Metric |
| ------------------- | ------------- | -------- | --------- | ------ |
| 101.25.67.0         | 255.255.255.0 | 10.0.0.2 | eth3      | 1      |
| default             | 0.0.0.0       | 10.0.0.1 | eth0      | 0      |
| 192.25.67.0         | 255.255.255.0 | 10.0.0.3 | eth5      | 10     |

**Each row is it's own Routing Entry**

| 192.25.67.0 | 255.255.255.0 | 10.0.0.3 | eth5 | 10  |
| ----------- | ------------- | -------- | ---- | --- |

**Concept:** GRE Tunneling is used to create a public connection between two L3 devices that would traditionally not be able to communicate directly without the assistance of other parties. This is done via the encapsulation of packets. By encapsulating packets with another packet that is using different protocols, we can create a "tunnel" between certain devices 

**Example** (https://www.cloudflare.com/learning/network-layer/what-is-gre-tunneling/):
For instance, suppose a company needs to set up a connection between the local area networks (LANs) in their two different offices. Both LANs use the latest version of the Internet Protocol, IPv6. But in order to get from one office network to another, traffic must pass through a network managed by a third party — which is somewhat outdated and only supports the older IPv4 protocol.

With GRE, the company could send traffic through this network by encapsulating IPv6 packets within IPv4 packets. Referring back to the analogy, the IPv6 packets are the car, the IPv4 packets are the ferry, and the third-party network is the water.

***

GRE Header Contents:
- GRE Header (4 Bytes): Protocol type used by the encapsulated packet
- IP Header (20 Bytes): Original packet header & payload

GRE will affect MTU so changes may needed to be made to the actual payload itself to allow for transmission without the use of a jumbo frame
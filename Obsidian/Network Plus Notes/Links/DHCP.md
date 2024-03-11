Function of **Dynamic Host Configuration Protocol**: DHCP is a network protocol that automates the process of assigning IP addresses and other network configuration information to devices on a network.
***
#### Key Concepts:
1. **IP Address Assignment:**
    - DHCP automatically assigns IP addresses to devices when they join a network. This dynamic assignment helps avoid conflicts and efficiently utilizes available IP address space.
2. **Lease Duration:**
    - IP addresses assigned by DHCP are not permanently assigned. Instead, they are leased for a specific duration. Devices must renew their lease before it expires if they want to continue using the same IP address.
3. **Configuration Information:**
    - DHCP can provide additional configuration information to devices, including:
        - Subnet mask
        - Default gateway (router)
        - Domain Name System (DNS) server
        - Domain name
        - DHCP server IP address
        - Lease duration
4. **Reduced Manual Configuration:**
    - DHCP eliminates the need for manual IP address configuration on each device, making it easier to manage large networks.
5. **Centralized Management:**
    - The DHCP server centrally manages IP address allocation, making it efficient to add, remove, or modify devices on the network without manual intervention.

#### How DHCP Works:
1. **DHCP Discover:**
    - When a device (such as a computer or smartphone) joins a network, it sends a DHCP Discover message to discover DHCP servers available on the network.
2. **DHCP Offer:**
    - DHCP servers respond with DHCP Offer messages, providing available IP addresses and configuration information. Multiple DHCP servers may respond, and the device selects one of the offers.
3. **DHCP Request:**
    - The device sends a DHCP Request message, confirming the selected DHCP server's offer.
4. **DHCP Acknowledge:**
    - The DHCP server sends a DHCP Acknowledge message, finalizing the IP address assignment and providing the device with the lease duration and additional configuration details.
5. **IP Address Lease Renewal:**
    - During the lease period, the device can continue using the assigned IP address. It may request a lease renewal before the current lease expires.
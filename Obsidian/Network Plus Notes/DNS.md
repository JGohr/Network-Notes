Function of DNS: Converts IP addresses to readable names for users to type instead

---

Full Qualified Domain Name (FQDN): ftp.diontraining.com 

5 Layers of domains:
- Root: Answers req in the root zone
- Top Level: .com
- Second Level: diontraining.com
- Sub domain: www.diontraining.com
- Host: Refers to specific machine

URL (Uniform Resource Locator)

Reverse Lookup: IP to Hostname
Forward Lookup: Hostname to IP
Name server: Type of DNS record that stores all the records for a given domain

Internal DNS: Allows cloud instances on the same network access each other using internal DNS names

External DNS Records created around the domain names from a central authority

TTL (Time To Live): Tells the DNS resolver how long to cache a query before req a new one

DNS Cache/Resolver: Makes a local copy of every DNS entry it resolves as you connect to the internet

Recursive Lookup: DNS server communicates with several other DNS servers to hunt down the IP addresses and return to the client

Iterative Lookup: Each DNS server responds directly to the client with an address for another DNS server that may have the correct address

| DNS Record | Desc           | Function                                            |
| ---------- | -------------- | --------------------------------------------------- |
| A          | Address        | Links a hostname to an IPv4 address                 |
| AAAA       | Address        | Links a hostname to an IPv6 address                 |
| CNAME      | Canonical Name | Points a domain to another domain or subdomain      |
| MX         | Mail Exchange  | Directs emails to a mail server                     |
| SOA        | Start Of Auth  | Stores important information about a domain or zone |
| PTR        | Pointer        | Correlates an IP address with a domain name         |
| TXT        | Text           | Adds text into the DNS                              |
| SRV        | Service        | Specifies a host and port for a specific service    |
| NS         | Name Server    | Indicates which DNS name server has the auth        |


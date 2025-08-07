# Common Protocols Summary

## Overview

Internet protocols are standardized rules defined in RFCs that enable consistent and reliable communication between devices over a network. The two main types of transport protocols are:

- **TCP (Transmission Control Protocol)** – connection-oriented, reliable
- **UDP (User Datagram Protocol)** – connectionless, faster, less reliable

---

## Transmission Control Protocol (TCP)

- Establishes a connection via a **Three-Way Handshake**.
- Maintains the connection throughout the data transfer.
- **Reliable** but slower due to connection overhead.

**Example:** Accessing a website (HTTP over TCP).

### Common TCP Protocols

| Protocol | Acronym | Port(s) | Description |
|---------|--------|--------|-------------|
| Telnet | Telnet | 23 | Remote login |
| SSH | Secure Shell | 22 | Secure remote login |
| SNMP | Simple Network Management Protocol | 161-162 | Manage network devices |
| HTTP | HyperText Transfer Protocol | 80 | Transfer webpages |
| HTTPS | HTTP Secure | 443 | Secure webpages |
| DNS | Domain Name System | 53 | Resolve domain names |
| FTP | File Transfer Protocol | 20-21 | File transfer |
| TFTP | Trivial File Transfer Protocol | 69 | File transfer |
| NTP | Network Time Protocol | 123 | Time sync |
| SMTP | Simple Mail Transfer Protocol | 25 | Email transfer |
| POP3 | Post Office Protocol | 110 | Retrieve emails |
| IMAP | Internet Message Access Protocol | 143 | Access emails |
| SMB | Server Message Block | 445 | File sharing |
| NFS | Network File System | 111, 2049 | Mount remote systems |
| BOOTP | Bootstrap Protocol | 67, 68 | Bootstrap systems |
| Kerberos | Kerberos | 88 | Authentication |
| LDAP | Lightweight Directory Access Protocol | 389 | Directory services |
| RADIUS | Remote Auth Dial-In User Service | 1812, 1813 | Authentication |
| DHCP | Dynamic Host Config Protocol | 67, 68 | IP assignment |
| RDP | Remote Desktop Protocol | 3389 | Remote desktop |
| NNTP | Network News Transfer Protocol | 119 | Newsgroups |
| RPC | Remote Procedure Call | 135, 137-139 | Remote procedure |
| Ident | Identification Protocol | 113 | User process ID |
| ICMP | Internet Control Message Protocol | 0-255 | Network troubleshooting |
| IGMP | Internet Group Management Protocol | 0-255 | Multicasting |
| Oracle-TNS | Oracle DB Listener | 1521/1526 | Oracle DB connections |
| Ingreslock | Ingres Lock | 1524 | Remote DB |
| Squid Proxy | HTTP Proxy | 3128 | Web caching proxy |
| SCP | Secure Copy Protocol | 22 | Secure file copy |
| SIP | Session Initiation Protocol | 5060 | VoIP sessions |
| SOAP | Simple Object Access Protocol | 80, 443 | Web services |
| SSL | Secure Sockets Layer | 443 | Secure data transfer |
| TCPW | TCP Wrappers | 113 | Access control |
| ISAKMP | ISAKMP | 500 | VPNs |
| MSSQL | Microsoft SQL Server | 1433 | DB connections |
| KINK | KINK | 892 | Authentication |
| OSPF | Open Shortest Path First | 89 | Routing |
| PPTP | Point-to-Point Tunneling Protocol | 1723 | VPN |
| REXEC | Remote Execution | 512 | Remote command exec |
| RLOGIN | Remote Login | 513 | Remote shell |
| X11 | X Window System | 6000 | GUI over network |
| DB2 | IBM DB2 | 50000 | RDBMS |

---

## User Datagram Protocol (UDP)

- Connectionless – sends packets without establishing a connection.
- **Faster**, but **unreliable**.

**Example:** Streaming video (e.g., YouTube).

### Common UDP Protocols

| Protocol | Acronym | Port(s) | Description |
|---------|--------|--------|-------------|
| DNS | Domain Name System | 53 | Resolve domain names |
| TFTP | Trivial File Transfer Protocol | 69 | File transfer |
| NTP | Network Time Protocol | 123 | Time sync |
| SNMP | Simple Network Management Protocol | 161 | Manage devices |
| RIP | Routing Information Protocol | 520 | Routing info exchange |
| IKE | Internet Key Exchange | 500, 11371 | IPsec Key Exchange |
| BOOTP | Bootstrap Protocol | 68 | Host bootstrap |
| DHCP | Dynamic Host Config Protocol | 67 | IP assignment |
| TELNET | Telnet | 23 | Remote access |
| MySQL | MySQL | 3306 | DB access |
| TS | Terminal Server | 3389 | Remote desktop |
| NetBIOS-NS | NetBIOS Name Service | 137 | LAN name resolution |
| MSSQL-M | SQL Server Browser | 1434 | MS SQL Server info |
| UPnP | Universal Plug and Play | 1900 | Device discovery |
| PostgreSQL | PGSQL | 5432 | DB access |
| VNC | Virtual Network Computing | 5900 | GUI sharing |
| X11 | X Window System | 6000–6063 | GUI sharing |
| SYSLOG | Syslog | 514 | Log messages |
| IRC | Internet Relay Chat | 194 | Chat protocol |
| OpenPGP | OpenPGP | 11371 | Encrypted data |
| XDMCP | X Display Manager Control Protocol | 177 | Remote GUI login |

---

## ICMP

Used for error reporting and diagnostics.

### ICMP Message Types

| Type | Description |
|------|-------------|
| Echo Request | Tests device reachability (e.g. `ping`) |
| Echo Reply | Responds to Echo Request |
| Timestamp Request | Gets time on remote device |
| Address Mask Request | Requests subnet mask |
| Destination Unreachable | Packet can't be delivered |
| Redirect | Suggests alternate route |
| Time Exceeded | TTL expired |
| Parameter Problem | Header issue |
| Source Quench | Traffic overload warning |

### ICMP Versions

- **ICMPv4**: For IPv4
- **ICMPv6**: For IPv6, includes improvements

### TTL (Time-To-Live)

- Limits packet's lifetime across routers.
- Helps detect routing loops and estimate hops.
- Default TTLs can hint at OS type:
  - Windows: 128
  - Linux/macOS: 64
  - Solaris: 255

---

## VoIP (Voice over Internet Protocol)

Enables voice/video communication over the Internet.

**Common Ports:**
- **TCP/UDP 5060, 5061**: SIP (most co  mmon)
- **TCP 1720**: H.323

### SIP Methods

| Method | Description |
|--------|-------------|
| INVITE | Starts session |
| ACK | Acknowledges INVITE |
| BYE | Ends session |
| CANCEL | Cancels INVITE |
| REGISTER | Registers client |
| OPTIONS | Checks capabilities |

### Information Disclosure via SIP

- SIP OPTIONS method can enumerate users or probe servers.
- Cisco VoIP systems use **SEPxxxx.cnf** files for configuration.

---

**End of Summary**
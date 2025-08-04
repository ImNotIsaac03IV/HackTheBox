
# IP Addresses

## Overview

Each host in a network is identified by a Media Access Control (MAC) address, which enables data exchange within the same network. However, to communicate across different networks, IP addresses (IPv4 or IPv6) are used. 

- **IPv4 / IPv6**: Unique postal address and district
- **MAC**: Exact floor and apartment within a building

Each IP address must be unique within a network.

---

## IPv4 Structure

- **32-bit binary number**
- Divided into four 8-bit groups (octets)
- Represented in decimal as: `127.0.0.1`
- Total possible IPv4 addresses: **4,294,967,296**

### IP Classes

| Class | Network Address | First Address | Last Address | Subnetmask | CIDR | Subnets | IPs            |
|-------|------------------|----------------|---------------|-------------|------|----------|-----------------|
| A     | 1.0.0.0          | 1.0.0.1        | 127.255.255.255 | 255.0.0.0   | /8   | 127      | 16,777,216      |
| B     | 128.0.0.0        | 128.0.0.1      | 191.255.255.255 | 255.255.0.0 | /16  | 16,384   | 65,536          |
| C     | 192.0.0.0        | 192.0.0.1      | 223.255.255.255 | 255.255.255.0 | /24 | 2,097,152| 256             |
| D     | 224.0.0.0        | 224.0.0.1      | 239.255.255.255 | Multicast   | -    | -        | Multicast       |
| E     | 240.0.0.0        | 240.0.0.1      | 255.255.255.255 | Reserved    | -    | -        | Reserved        |

---

## Subnet Mask

Defines which part of the IP address is the **network** and which is the **host**. The subnet mask is the same length as the IP address.

---

## Network and Gateway Addresses

- **Network Address**: Reserved IP representing the network
- **Broadcast Address**: Sends messages to all devices in the network
- **Default Gateway**: Router IP address connecting subnets

---

## Broadcast Address

- A special IP used to send data to **all** hosts in a subnet.
- Last IP in the subnet range.

---

## Binary System

IPv4 = 4 octets (8 bits each). Each bit has a specific decimal value.

### Example:

**IPv4 Address: 192.168.10.39**

**Binary Conversion:**

| Octet | Binary             | Decimal Sum |
|-------|--------------------|-------------|
| 1st   | 11000000           | 192         |
| 2nd   | 10101000           | 168         |
| 3rd   | 00001010           | 10          |
| 4th   | 00100111           | 39          |

---

## Subnet Mask (Example)

**Decimal:** 255.255.255.0  
**Binary:** 11111111.11111111.11111111.00000000

---

## CIDR (Classless Inter-Domain Routing)

CIDR replaces traditional IP class division. It uses a suffix (e.g., `/24`) to represent the number of bits in the subnet mask.

### Example:

- **IPv4 Address**: `192.168.10.39`
- **Subnet Mask**: `255.255.255.0`
- **CIDR Notation**: `192.168.10.39/24`

This means the first 24 bits are the network part.

---


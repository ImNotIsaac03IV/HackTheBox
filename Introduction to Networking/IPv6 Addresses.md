
# IPv6 Addresses

IPv6 is the successor of IPv4. Unlike IPv4, the IPv6 address is 128-bit long. The prefix identifies the host and network parts. The Internet Assigned Numbers Authority (IANA) is responsible for assigning IPv4 and IPv6 addresses and their associated network portions. IPv6 is expected to eventually replace IPv4, although both can be used simultaneously through Dual Stack.

## Key Features of IPv6

- Larger address space (128-bit)
- Address self-configuration (SLAAC)
- Multiple IPv6 addresses per interface
- Faster routing
- End-to-end encryption (IPsec)
- Data packages up to 4 GB

### IPv4 vs IPv6

| Feature             | IPv4            | IPv6                                |
|---------------------|------------------|--------------------------------------|
| Bit length          | 32-bit           | 128-bit                              |
| OSI Layer           | Network Layer    | Network Layer                        |
| Addressing range    | ~4.3 billion     | ~340 undecillion                     |
| Representation      | Binary           | Hexadecimal                          |
| Prefix notation     | 10.10.10.0/24    | fe80::dd80:b1a9:6687:2d3b/64         |
| Dynamic addressing  | DHCP             | SLAAC / DHCPv6                       |
| IPsec               | Optional         | Mandatory                            |

## Types of IPv6 Addresses

| Type     | Description                                                                 |
|----------|-----------------------------------------------------------------------------|
| Unicast  | Addresses for a single interface.                                           |
| Anycast  | Addresses for multiple interfaces; only one receives the packet.           |
| Multicast| Addresses for multiple interfaces; all receive the same packet.            |

> **Note:** IPv6 does not use broadcast addresses; it uses multicast instead.

## Hexadecimal System

The hexadecimal system is used to make binary representation more readable.

| Decimal | Hex | Binary  |
|---------|-----|---------|
| 1       | 1   | 0001    |
| 2       | 2   | 0010    |
| 3       | 3   | 0011    |
| ...     | ... | ...     |
| 10      | A   | 1010    |
| 15      | F   | 1111    |

### Example: IPv4 Address in Hexadecimal

IPv4: `192.168.12.160`

| Octet       | Binary       | Hex |
|-------------|--------------|-----|
| 1st         | 11000000     | C0  |
| 2nd         | 10101000     | A8  |
| 3rd         | 00001100     | 0C  |
| 4th         | 10100000     | A0  |

## IPv6 Address Format

An IPv6 address is 128 bits (16 bytes), written in hexadecimal, divided into 8 blocks separated by colons `:`.

### Example

- Full: `fe80:0000:0000:0000:dd80:b1a9:6687:2d3b/64`
- Short: `fe80::dd80:b1a9:6687:2d3b/64`

### Parts of an IPv6 Address

1. **Network Prefix** – identifies the network/subnet
2. **Interface Identifier (Suffix)** – identifies the host (often derived from MAC)

### Typical Prefix Lengths

- `/64` (default)
- `/56`, `/48`, `/32` (for custom networks)

## RFC 5952 – Notation Rules

- Alphabetical characters are lowercase.
- Leading zeros are omitted.
- One set of consecutive `0000` blocks can be replaced with `::` (once per address).


# MAC Addresses

## MAC Addresses

- A **MAC (Media Access Control)** address is a 48-bit unique identifier assigned to network interfaces.
- Used in Ethernet (IEEE 802.3), Bluetooth (IEEE 802.15), and WLAN (IEEE 802.11).
- Composed of:
  - **OUI (Organizationally Unique Identifier)** – first 3 bytes (manufacturer-defined)
  - **NIC (Network Interface Controller)** – last 3 bytes (device-specific)
- Represented in hexadecimal (e.g., `DE:AD:BE:EF:13:37`)

### Address Types

- **Unicast**: Sent to a single receiver (bit 0 of first octet = 0)
- **Multicast**: Sent to multiple hosts (bit 0 = 1)
- **Broadcast**: Sent to all hosts (`FF:FF:FF:FF:FF:FF`)
- **Global vs Local**:
  - Global: IEEE-assigned
  - Local: Manually set (bit 1 of first octet = 1)

## Address Resolution Protocol (ARP)

- Resolves IP (Layer 3) to MAC (Layer 2) addresses within a LAN.
- Two key message types:
  - **ARP Request**: "Who has IP X? Tell IP Y"
  - **ARP Reply**: "IP X is at MAC Z"

### Tshark ARP Example

```
1 10.129.12.100 -> 10.129.12.255 ARP Who has 10.129.12.101? Tell 10.129.12.100
2 10.129.12.101 -> 10.129.12.100 ARP 10.129.12.101 is at AA:AA:AA:AA:AA:AA
```

## Attacks and Security

### MAC Spoofing
- Attacker forges MAC to impersonate another device.

### MAC Flooding
- Overwhelms switches with fake MACs to degrade performance.

### ARP Spoofing (ARP Cache Poisoning)
- Sends false ARP replies to redirect traffic through attacker.
- Used in **MITM (Man-In-The-Middle)** attacks.

#### Example of ARP Spoofing
```
1 Attacker -> Target ARP 10.129.12.101 is at AA:AA:AA:AA:AA:AA (fake)
2 Target -> Broadcast ARP Who has 10.129.12.101?
3 10.129.12.101 -> Target ARP 10.129.12.101 is at BB:BB:BB:BB:BB:BB (real)
4 Attacker -> Target ARP 10.129.12.101 is at AA:AA:AA:AA:AA:AA (again)
```

### Countermeasures
- Use secure protocols (IPSec, SSL)
- Enable port security on switches
- Use firewalls and intrusion detection systems (IDS)

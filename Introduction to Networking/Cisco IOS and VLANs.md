
# Cisco IOS and VLANs: A Study Guide

## Cisco IOS Overview

**Cisco IOS** is the operating system used on Cisco network devices like routers and switches. Key features include:

- IPv6 support
- Quality of Service (QoS)
- Encryption & Authentication security features
- Virtualization (e.g., VPLS, VRF)
- Protocol support (OSPF, BGP, DHCP, VTP, STP)

### Access Methods

- **CLI (Command Line Interface)** – primary management method
- **GUI** – available on some platforms
- **Remote access** via **SSH or Telnet**

### Password Types

| Password Type   | Description |
|------------------|-------------|
| User             | For basic login |
| Enable           | For entering privileged EXEC mode |
| Secret           | For securing access to services |
| Enable Secret    | Encrypted, secure access to enable mode |

---

## VLANs (Virtual Local Area Networks)

**VLAN** allows network segmentation at Layer 2, improving organization, performance, and security.

### Example VLAN Setup

| Department | VLAN ID | Subnet             |
|------------|---------|--------------------|
| Servers    | 10      | 192.168.1.0/24     |
| C-Level    | 20      | 192.168.2.0/24     |
| Finance    | 30      | 192.168.3.0/24     |
| HR         | 40      | 192.168.4.0/24     |
| Marketing  | 50      | 192.168.5.0/24     |
| Support    | 60      | 192.168.6.0/24     |

### VLAN Ranges

- **1-1005**: Normal-range (saved in `vlan.dat`)
- **1006-4094**: Extended-range (not saved by default)

### Membership Types

- **Static VLANs**: Manually assigned; more secure
- **Dynamic VLANs**: Assigned via MAC/protocol; less secure

### Port Types

- **Access Ports**: Single VLAN only
- **Trunk Ports**: Multiple VLANs

---

## VLAN Tagging

### IEEE 802.1Q

Adds a 4-byte VLAN tag inside Ethernet frame. Key fields:

- **TPID**: Always `0x8100`
- **VID**: 12-bit VLAN ID (0 and 4095 reserved)
- Supports **4094 VLANs**

### ISL (Inter-Switch Link)

- Cisco proprietary trunking protocol (deprecated)

### Double Tagging

- Embeds 2 VLAN tags for attacks or legitimate use (e.g., ISPs)

---

## Assigning VLANs to NICs

### Linux (using `ip` command)

```bash
sudo modprobe 8021q
sudo ip link add link eth0 name eth0.20 type vlan id 20
sudo ip addr add 192.168.1.1/24 dev eth0.20
sudo ip link set up eth0.20
```

### Windows (via PowerShell)

```powershell
Set-NetAdapter -Name "Ethernet 2" -VlanID 10
```

---

## VLAN Analysis

### Wireshark Filters

- `vlan`: All tagged packets
- `vlan.id == 10`: Filter for VLAN 10

### Tshark Example

```bash
tshark -r file.pcapng -T fields -e vlan.id | sort -n -u
```

---

## VLAN Attacks

### VLAN Hopping

- Exploits **DTP** (Dynamic Trunking Protocol)
- Tools: Yersinia

### Double Tagging

- Sends frames with nested 802.1Q tags to traverse VLAN boundaries
- Tools: Scapy, Yersinia

---

## VXLAN (Virtual eXtensible LAN)

- Overlay network over Layer 3
- Uses **24-bit VXLAN Network Identifier (VNI)** – supports **16 million segments**
- Solves VLAN scalability and STP limitations

---

## Cisco Discovery Protocol (CDP)

- Layer 2 protocol for Cisco device discovery
- Shows: device ID, IP, port ID, platform, etc.

## Spanning Tree Protocol (STP)

- Prevents Layer 2 loops in networks
- Variants: 802.1D, 802.1w (Rapid STP)

---

**End of Summary**

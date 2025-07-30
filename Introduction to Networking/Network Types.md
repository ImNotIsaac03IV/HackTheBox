
# Network Types

Each network is structured differently and can be set up individually. For this reason, so-called types and topologies have been developed that can be used to categorize these networks. When reading about all the types of networks, it can be a bit of information overload as some network types include the geographical range. We rarely hear some of the terminologies in practice, so this section will be broken up into **Common Terms** and **Book Terms**.

---

## Common Terminology

| Network Type         | Definition                                         |
|----------------------|----------------------------------------------------|
| Wide Area Network (WAN) | Internet                                        |
| Local Area Network (LAN) | Internal Networks (Ex: Home or Office)         |
| Wireless Local Area Network (WLAN) | Internal Networks accessible over Wi-Fi |
| Virtual Private Network (VPN) | Connects multiple network sites to one LAN |

---

### WAN

The WAN (Wide Area Network) is commonly referred to as **The Internet**. When dealing with networking equipment, we'll often have a WAN Address and LAN Address. The WAN one is the address that is generally accessed by the Internet. A WAN is just a large number of LANs joined together. Large companies or government agencies may also have an "Internal WAN" (aka Intranet, Airgap Network). A network is typically considered a WAN if:

- It uses WAN-specific routing protocols (e.g., BGP)
- The IP schema used is **not** within RFC 1918 ranges

---

### LAN / WLAN

LANs and WLANs typically assign IP addresses within:

- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

WLANs are simply LANs with wireless capabilities. This primarily adds a **security designation**.

---

### VPN

Virtual Private Networks (VPNs) make the user appear as if they are connected directly to a remote LAN.

#### Site-to-Site VPN

- Network devices (usually routers or firewalls) on both ends
- Joins entire network ranges

#### Remote Access VPN

- Creates a virtual interface (e.g., TUN Adapter via OpenVPN)
- Used by Hack The Box to access labs
- **Split-Tunnel VPNs** only route specific traffic through VPN
- Split tunneling is good for privacy (like in HTB) but **bad for corporate environments**

#### SSL VPN

- Browser-based VPN
- Streams applications or desktops
- Example: Hack The Box Pwnbox

---

## Book Terms

| Network Type         | Definition                                        |
|----------------------|---------------------------------------------------|
| Global Area Network (GAN) | Global network (the Internet)               |
| Metropolitan Area Network (MAN) | Regional network (multiple LANs)     |
| Wireless Personal Area Network (WPAN) | Personal network (Bluetooth)    |

---

### GAN (Global Area Network)

- Worldwide networks such as the Internet
- Also includes private international networks (e.g., corporate networks)
- Connects via undersea cables or satellites

---

### MAN (Metropolitan Area Network)

- Broadband network connecting LANs in proximity
- Typically used to connect company branches via leased lines
- Uses high-performance routers and fiber
- Faster than the Internet

---

### PAN / WPAN

- **PAN**: Personal Area Network via cable
- **WPAN**: Wireless Personal Area Network via Bluetooth, Wireless USB
- **Piconet**: Bluetooth-based WPAN

Used in:

- **IoT and Smart Home tech**
- **Protocols**: Insteon, Z-Wave, ZigBee

---

These network types help define the scope and security posture of communication between systems, ranging from personal devices to global-scale infrastructure.

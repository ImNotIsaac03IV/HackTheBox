
# Networking Topologies

## Introduction

A **network topology** refers to the typical arrangement and the physical or logical connection of devices in a network. Devices include hosts (clients, servers) and network components (switches, routers, bridges).

- **Physical Topology**: Actual layout of cables and nodes.
- **Logical Topology**: Path that the data takes within the network.

---

## 1. Connections

| Wired Connections         | Wireless Connections |
|--------------------------|----------------------|
| Coaxial cabling          | Wi-Fi                |
| Glass fiber cabling      | Cellular             |
| Twisted-pair cabling     | Satellite            |

---

## 2. Nodes - Network Interface Controllers (NICs)

- Repeaters
- Hubs
- Bridges
- Switches
- Router/Modem
- Gateways
- Firewalls

Nodes act as connection points for data transmission and may vary in complexity.

---

## 3. Classifications

Topologies can be physical or logical and are categorized into 8 types:

### Point-to-Point

- Direct connection between two devices.
- Simplest form, used in traditional telephony.

### Bus

- Shared transmission medium.
- One host transmits while others receive.
- No central controller.

### Star

- Central device (hub/switch/router) connects all hosts.
- Data travels through the central device.

### Ring

- Hosts connected in a circular manner.
- Uses a token for transmission control.
- May be physical or logical ring.

### Mesh

- Every node connects to every other node (fully meshed) or some nodes (partially meshed).
- Common in WANs and MANs for redundancy and reliability.

### Tree

- Hierarchical structure of star networks.
- Used in large networks like company buildings and MANs.

### Hybrid

- Combination of two or more topologies.
- E.g., star + bus or tree + ring.

### Daisy Chain

- Devices connected linearly from one to another.
- Often used in automation systems.

---

## Summary

Network topologies dictate how devices connect and communicate:
- **Point-to-Point**: Simple and direct.
- **Bus**: Shared medium, no central device.
- **Star**: Centralized communication.
- **Ring**: Circular data path.
- **Mesh**: Redundant and reliable.
- **Tree**: Structured and scalable.
- **Hybrid**: Flexible combinations.
- **Daisy Chain**: Linear connections.

Choosing the right topology depends on the network's scale, purpose, and required reliability.

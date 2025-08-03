# Network Layer (Layer 3)

The **network layer** (Layer 3) of OSI controls the exchange of data packets, as these cannot be directly routed to the receiver and therefore have to be provided with routing nodes. The data packets are then transferred from node to node until they reach their target.

To implement this, the network layer:

- Identifies individual network nodes
- Sets up and clears connection channels
- Manages routing and data flow control

When sending the packets:

- Addresses are evaluated
- Data is routed through the network from node to node
- Nodes typically do not process data from layers above Layer 3

### Key Responsibilities

- **Logical Addressing**
- **Routing**

### Protocols at the Network Layer

Protocols are defined in each OSI layer, and these protocols represent a set of communication rules. Some protocols span multiple layers. The most used protocols on Layer 3 include:

- **IPv4 / IPv6**
- **IPsec**
- **ICMP**
- **IGMP**
- **RIP**
- **OSPF**

### Functionality

The Network Layer ensures the routing of packets from the source to the destination both within and outside of subnets. These subnets may use different or incompatible addressing schemes.

In these cases:

- Data transmission must go through the entire communication network
- Packets are routed through network nodes (e.g., routers)
- These routers forward packets without sending them to higher OSI layers
- Each router assigns a new intermediate destination and sends packets to the next node

This layer makes it possible to maintain communication even when direct routing between the sender and receiver is not feasible.

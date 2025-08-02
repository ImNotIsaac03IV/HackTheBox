# The TCP/IP Model

The TCP/IP model is a layered reference model, often referred to as the Internet Protocol Suite. The term **TCP/IP** stands for the two protocols:

- **Transmission Control Protocol (TCP)** – Layer 4 (Transport)
- **Internet Protocol (IP)** – Layer 3 (Network)

## Layers of the TCP/IP Model

| Layer       | Function |
|-------------|----------|
| **4. Application** | Allows applications to access the other layers' services and defines the protocols applications use to exchange data. |
| **3. Transport**   | Responsible for providing (TCP) session and (UDP) datagram services for the Application Layer. |
| **2. Internet**    | Responsible for host addressing, packaging, and routing functions. |
| **1. Link**        | Responsible for placing the TCP/IP packets on the network medium and receiving corresponding packets from it. TCP/IP is designed to work independently of the network access method, frame format, and medium. |

With TCP/IP, every application can transfer and exchange data over any network, regardless of the receiver's location. IP ensures data packet delivery, and TCP manages data transfer, ensuring a stable connection between data stream and application.

## OSI vs. TCP/IP Model

- **OSI Model:** 7 Layers (Application, Presentation, Session, Transport, Network, Data-Link, Physical)
- **TCP/IP Model:** 4 Layers (Application, Transport, Internet, Link)

## Key Tasks and Protocols of TCP/IP

| Task                | Protocol | Description |
|---------------------|----------|-------------|
| **Logical Addressing** | IP       | Structures the network topology with logical addressing (e.g., subnetting, CIDR). |
| **Routing**           | IP       | Determines the next node for each packet from sender to receiver. |
| **Error & Control Flow** | TCP   | Maintains virtual connections and sends control messages to verify connectivity. |
| **Application Support** | TCP   | Uses TCP and UDP ports to differentiate application communication links. |
| **Name Resolution**     | DNS   | Resolves Fully Qualified Domain Names (FQDNs) to IP addresses. |

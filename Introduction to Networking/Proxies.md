# Proxies

## What is a Proxy?

A **proxy** is a device or service that acts as a **mediator** between a client and another server, meaning it **intercepts and inspects traffic**. It must be able to inspect contents—otherwise, it's a gateway, not a proxy.

### Misconceptions

- **Average users**: Think proxies just change IP addresses (often confuse VPNs with proxies).
- **Security professionals**: Think of tools like BurpSuite or SOCKS/SSH pivoting.
- **Web developers**: Think of protection via Cloudflare or ModSecurity.
- **Law enforcement**: Often associate proxies with illegal activity.

## Key Concept

**Proxies operate at Layer 7 (Application Layer) of the OSI Model.**

---

## Types of Proxies

### 1. Dedicated Proxy / Forward Proxy

A **forward proxy** is when a client makes a request, and the proxy executes it on their behalf.

#### Example Use Cases

- Corporate environments to control Internet access.
- BurpSuite used to forward and inspect HTTP requests.
- Malware detection and prevention via proxy-aware requirements.

#### Behavior with Web Browsers

- **IE, Edge, Chrome**: Follow system proxy settings (WinSock).
- **Firefox**: Uses `libcurl`, ignores system proxy, making malware less likely to work.

#### Forward Proxy Security Note

- Malware must either be proxy-aware or use alternate channels like **DNS as C2**.
- DNS traffic can be detected using tools like **Sysmon**.

---

### 2. Reverse Proxy

A **reverse proxy** handles **incoming** traffic, unlike the forward proxy.

#### Example Use Cases

- **Cloudflare**: Protects sites from DDoS attacks and filters traffic.
- **Penetration Testing**: Reverse proxies on infected endpoints redirect traffic back to attackers.
- **Web Application Firewalls (WAF)**: Tools like **ModSecurity** or **Cloudflare WAF** inspect incoming web requests.

#### Benefits

- Bypass firewall and avoid IDS logging by routing traffic through compromised hosts or tunnels.

---

### 3. Transparent vs Non-Transparent Proxies

| Type | Description |
|------|-------------|
| **Transparent Proxy** | Client is unaware. Proxy intercepts communication silently. |
| **Non-Transparent Proxy** | Client/software must be configured to use it explicitly. No configuration = no Internet. |

#### Real-World Example

- **Transparent**: ISP or enterprise network filters traffic without user input.
- **Non-Transparent**: Firefox requires manual proxy configuration.

---

## Summary

| Proxy Type | Direction | Visibility | Example |
|------------|-----------|------------|---------|
| Forward Proxy | Outgoing | Client-aware | Corporate proxies, BurpSuite |
| Reverse Proxy | Incoming | Often invisible | Cloudflare, ModSecurity |
| Transparent | Both | Client-unaware | Network-based filtering |
| Non-Transparent | Both | Client-aware | Manual browser configuration |

Proxies play a critical role in **security**, **privacy**, and **traffic management**, and understanding them helps build effective networks and security policies.

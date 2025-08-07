# Wireless Networks - Study Guide

## Overview
Wireless networks enable devices to communicate over the air without physical cables, using **radio frequency (RF)** signals. Devices use **wireless adapters** to transmit and receive these signals.

## Types of Wireless Networks
- **WiFi (WLAN):** Covers small areas (e.g., home or office); uses 2.4 GHz or 5 GHz bands.
- **WWAN:** Covers large areas using cellular networks (3G, 4G, 5G).

## Connecting to WiFi
To connect:
- Device must be within range and have correct settings (SSID, password).
- Uses **IEEE 802.11** protocol.
- Communication involves **Wireless Access Point (WAP)**.

### Connection Process (IEEE 802.11)
- **Association Request:** Device → WAP with details like MAC address, SSID, supported rates/channels/security.
- **WAP grants access**, allowing communication and Internet access.

## Communication
- Devices request permission from WAP before transmitting.
- RF signals are used to send/receive data.
- **Techniques like spread spectrum and error correction** handle interference.

## WEP Challenge-Response Handshake
| Step | Entity   | Description |
|------|----------|-------------|
| 1    | Client   | Sends association request to WAP |
| 2    | WAP      | Sends challenge string |
| 3    | Client   | Responds using shared key |
| 4    | WAP      | Validates response, grants access |

- Uses **CRC (Cyclic Redundancy Check)** for error detection.
- **Flaw:** CRC uses plaintext for calculations, allowing decryption of packets without the key.

## Security Features
### 1. **Encryption**
- **WEP:** 40/104-bit key + RC4; vulnerable to attacks.
- **WPA2/WPA3:** Stronger, uses AES.

### 2. **Access Control**
- Devices authenticated using passwords or MAC addresses.

### 3. **Firewall**
- Built into most routers, filters traffic based on rules.

## Encryption Protocols
| Protocol | IV Size | Secret Key Size | Cipher |
|----------|---------|-----------------|--------|
| WEP-40   | 24-bit  | 40-bit          | RC4    |
| WEP-104  | 24-bit  | 80-bit          | RC4    |

- **WEP is insecure** due to small IV, shared key usage.
- **WPA uses AES**, PSK or 802.1X authentication.

## Authentication Protocols
### LEAP
- Uses shared keys (less secure).

### PEAP
- Uses **TLS tunneling + digital certificates** (more secure).

### TACACS+
- Central authentication server for devices (e.g., routers).
- Encrypts entire authentication packet.

## Disassociation Attack
- Sends **disassociation frames** to clients to disconnect them from WAP.
- Used to **disrupt** or set up **further attacks** (e.g., MITM).

## Wireless Hardening Techniques
- **Disable SSID broadcasting:** Hides network from general scans.
- **Use WPA2/WPA3:** Ensures encryption and authentication.
- **MAC Filtering:** Allows only approved devices.
- **Deploy EAP-TLS:** Uses certificates for strong authentication and encryption.

---

**Study Tips:**
- Memorize protocols and their purposes (WEP vs WPA2 vs WPA3).
- Understand handshake processes (WEP, IEEE 802.11).
- Focus on vulnerabilities (e.g., CRC flaw, small IVs).
- Practice configuring a secure WiFi setup using WPA3 and EAP-TLS.

# Hypertext Transfer Protocol Secure (HTTPS)

## Overview
HTTPS is the secure version of HTTP. Unlike HTTP, which transmits data in clear-text, HTTPS encrypts all communication between the client (browser) and the server to prevent Man-in-the-Middle (MiTM) attacks.  

- **HTTP risk:** Data like usernames and passwords can be intercepted on public networks.  
- **HTTPS benefit:** Data is encrypted, making interception useless without the decryption key.  
- **Identification:** Websites using HTTPS can be recognized by `https://` in the URL and a lock icon in the browser.  

> **Note:** Even with HTTPS, using a clear-text DNS server can reveal the visited URL. Using encrypted DNS (e.g., 8.8.8.8, 1.1.1.1) or a VPN is recommended.

---

## HTTPS Flow (High-Level)
1. User requests `http://example.com`.  
2. Server responds with **HTTP 301 redirect** to `https://example.com`.  
3. Browser connects to port 443 and performs a **TLS handshake**:
   - Client Hello → Server Hello → SSL certificate exchange → Key verification.  
4. Encrypted communication begins after a successful handshake.  

> **Security Note:** HTTP downgrade attacks can force a browser to use HTTP, but modern browsers and servers typically protect against this.

---

## cURL with HTTPS
- By default, `cURL` handles HTTPS, performing the handshake and encrypting/decrypting automatically.  
- Invalid SSL certificates prevent communication to avoid MiTM attacks:  

\`\`\`bash
curl https://example.com
# May show: SSL certificate problem: Invalid certificate chain
\`\`\`

- To skip SSL verification (useful for testing local or practice web applications), use the `-k` flag:

\`\`\`bash
curl -k https://example.com
\`\`\`

---

## Key Points
- HTTPS encrypts HTTP traffic to protect sensitive data.  
- Encrypted traffic cannot be easily intercepted.  
- Browsers and tools like `cURL` verify SSL certificates by default.  
- Optional flags (like `-k`) bypass SSL checks for testing purposes.  

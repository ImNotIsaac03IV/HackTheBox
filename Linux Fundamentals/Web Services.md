
# Working with Web Services in Linux

## Overview

Understanding web services on Linux is essential for both development and penetration testing. This guide explores installing, configuring, and interacting with web servers like Apache and tools like `curl`, `wget`, and Python's `http.server`.

---

## Apache Web Server

### Installation

```bash
sudo apt install apache2 -y
```

### Starting Apache

```bash
sudo systemctl start apache2
```

### Default Page

Visit `http://localhost` to confirm Apache is running (you should see an "It works!" message).

### Change Listening Port

Edit `/etc/apache2/ports.conf`:

```conf
Listen 8080
```

Then restart Apache:

```bash
sudo systemctl restart apache2
```

Access via: `http://localhost:8080`

---

## Command Line Tools

### `curl`

Use `curl` to interact with web servers and inspect responses.

```bash
curl http://localhost
```

Returns raw HTML source of the page.

### `wget`

Use `wget` to download web content.

```bash
wget http://localhost
```

Saves as `index.html` by default.

---

## Python HTTP Server

### Start a Simple HTTP Server

```bash
python3 -m http.server
```

Default port is 8000. Visit `http://localhost:8000`

### Example Output

```bash
127.0.0.1 - - [15/May/2020 17:56:29] "GET /readme.html HTTP/1.1" 200 -
```

---

## Apache Modules

| Module       | Purpose                                                   |
|--------------|-----------------------------------------------------------|
| `mod_ssl`    | Encrypts communication (HTTPS)                            |
| `mod_proxy`  | Routes requests (useful in reverse proxies)               |
| `mod_headers`| Modify HTTP headers                                       |
| `mod_rewrite`| Dynamically rewrite URLs                                  |

---

## Tips for Learning

- Explore beyond comfort zones
- Perform independent research
- Practice creative problem solving

---

> _"This is not an exam—it's training for real-world problem solving."_ 🚀


# HyperText Transfer Protocol (HTTP) Summary

## Overview
HTTP is an **application-level protocol** used to access resources on the World Wide Web. "Hypertext" refers to text containing links to other resources, making it easy for users to navigate.

HTTP communication involves:
- **Client**: Requests a resource.
- **Server**: Processes the request and returns the resource.

**Default HTTP port:** 80 (can be changed via server configuration).

---

## URL (Uniform Resource Locator)
A URL specifies the resource to be accessed over HTTP. Example:

```
http://admin:password@inlanefreight.com:80/dashboard.php?login=true#status
```

### URL Components
| Component      | Example                    | Description |
|----------------|----------------------------|-------------|
| Scheme         | http://, https://          | Identifies the protocol; ends with `://` |
| User Info      | admin:password@            | Optional credentials for authentication |
| Host           | inlanefreight.com          | Hostname or IP address of the resource |
| Port           | :80                        | Defaults: 80 for HTTP, 443 for HTTPS |
| Path           | /dashboard.php             | Resource path (file or folder) |
| Query String   | ?login=true                | Parameters and values; multiple separated by `&` |
| Fragment       | #status                    | Browser-side section within the resource |

**Mandatory fields:** Scheme and Host.

---

## HTTP Flow
1. User enters a URL in the browser.
2. Browser sends a **DNS query** to resolve the domain to an IP.
   - Local `/etc/hosts` is checked first.
3. Browser sends an HTTP **GET request** to the server (default port 80).
4. Server processes the request and returns the resource (default `index.html`).
5. Response includes **status code** (e.g., `200 OK`).
6. Browser renders the content.

---

## cURL
cURL is a **command-line tool** to send HTTP requests. Useful for penetration testing and automation.

### Basic Usage
```bash
curl inlanefreight.com
```
- Outputs raw HTML instead of rendering.

### Downloading Files
```bash
curl -O inlanefreight.com/index.html   # Uses remote file name
curl -o custom.html inlanefreight.com/index.html  # Custom file name
curl -s -O inlanefreight.com/index.html  # Silent download
```

### Common Flags
| Flag       | Description |
|------------|-------------|
| -d, --data | HTTP POST data |
| -i, --include | Include response headers |
| -o, --output | Write output to file |
| -O, --remote-name | Save file using remote name |
| -s, --silent | Silent mode |
| -u, --user | Specify user credentials |
| -A, --user-agent | Send custom User-Agent |
| -v, --verbose | Verbose output |
| -h, --help | Get help for commands |

**Tip:** Use `man curl` or `--help all` for full documentation.

---

**Note:** This summary focuses on HTTP web requests. For more on HTML/web applications, refer to an Introduction to Web Applications module.

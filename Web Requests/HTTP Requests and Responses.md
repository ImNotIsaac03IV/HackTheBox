
# HTTP Requests and Responses

HTTP communications mainly consist of an HTTP **request** and an HTTP **response**.  

- **Client** (e.g., browser, cURL) sends an HTTP request.  
- **Server** (e.g., web server) processes the request and returns an HTTP response.  

---

## HTTP Request

An HTTP request contains:  
- The **resource** being requested (URL/path/parameters)  
- Optional **data or body**  
- **Headers** and other options  

### Example HTTP GET Request
```http
GET /users/login.html HTTP/1.1
Host: inlanefreight.com
User-Agent: Mozilla/5.0
Cookie: PHPSESSID=c4ggt4jull9obt7aupa55o8vbf
```

#### Request Line Fields
| Field   | Example                  | Description |
|---------|--------------------------|-------------|
| Method  | GET                      | Action type (GET, POST, etc.) |
| Path    | /users/login.html        | Resource path, can include query string |
| Version | HTTP/1.1                 | HTTP protocol version |

#### Headers
- Provide additional information for the server  
- Examples: `Host`, `User-Agent`, `Cookie`  
- Terminated by a new line before the body  

> Note: HTTP/1.X sends requests in clear-text. HTTP/2.X uses binary format.

---

## HTTP Response

The server processes the request and sends back a response.

### Example HTTP Response
```http
HTTP/1.1 200 OK
Date: Tue, 21 Jul 2020 05:20:15 GMT
Server: Apache/2.4.41
Set-Cookie: PHPSESSID=m4u64rqlpfthrvvb12ai9voqgf
Content-Type: text/html; charset=UTF-8

<!DOCTYPE html>
<html>...</html>
```

#### Response Line
- **Version**: HTTP version (e.g., HTTP/1.1)  
- **Status**: HTTP status code (e.g., 200 OK)

#### Response Components
- **Headers**: Provide metadata about the response  
- **Body**: Contains resource data (HTML, JSON, images, PDFs, etc.)

---

## Using cURL

cURL allows you to preview both HTTP requests and responses.

### Example: Verbose Mode
```bash
curl inlanefreight.com -v
```

#### Output Highlights
- **Request**
```
> GET / HTTP/1.1
> Host: inlanefreight.com
> User-Agent: curl/7.65.3
> Accept: */*
```
- **Response**
```
< HTTP/1.1 401 Unauthorized
< Date: Tue, 21 Jul 2020 05:20:15 GMT
< Server: Apache/X.Y.ZZ (Ubuntu)
< WWW-Authenticate: Basic realm="Restricted Content"
< Content-Length: 464
< Content-Type: text/html; charset=iso-8859-1
```

> Exercise: Use `-vvv` with cURL to see more detailed request/response information.

---

## Browser Developer Tools (DevTools)

- Built-in tools for monitoring HTTP requests/responses  
- Open DevTools in Chrome/Firefox: `CTRL+SHIFT+I` or `F12`  
- Focus on the **Network tab** to track requests

### Features
- Shows **request method** (GET/POST), **URL**, **path**, and **response status**  
- Can filter requests for easier inspection  
- Click a request → **Response tab** → **Raw** to see unrendered response body

> Exercise: Explore the Network tab to inspect HTTP traffic for a website.

---

## Key Takeaways

- HTTP request: method + path + version + headers + optional body  
- HTTP response: version + status code + headers + optional body  
- cURL `-v` helps view full HTTP requests/responses  
- Browser DevTools is essential for monitoring web traffic  

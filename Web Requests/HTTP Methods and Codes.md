# HTTP Methods and Status Codes: Learning Guide

HTTP supports multiple methods to access resources, allowing clients to send data, forms, or files to the server. These methods instruct the server how to handle requests.

## HTTP Request Methods

| Method  | Description |
|---------|-------------|
| GET     | Requests a specific resource. Can pass data via URL query strings (e.g., `?param=value`). |
| POST    | Sends data to the server (text, PDFs, binary). Data goes in the request body. Common for forms, logins, and uploads. |
| HEAD    | Requests headers only (no body). Useful to check response length before downloading resources. |
| PUT     | Creates new resources on the server. Must be secured to prevent malicious uploads. |
| DELETE  | Deletes an existing resource. If unsecured, may allow DoS by removing critical files. |
| OPTIONS | Returns information about supported methods on the server. |
| PATCH   | Applies partial modifications to a resource. |

**Note:** Most web applications mainly use GET and POST. REST APIs often use PUT and DELETE for updating or removing data.

---

## HTTP Status Codes

HTTP status codes indicate the result of a request. They are grouped into five classes:

| Class | Description |
|-------|-------------|
| 1xx   | Informational. Does not affect request processing. |
| 2xx   | Success. Request was successfully processed. |
| 3xx   | Redirection. Server directs client to another URL. |
| 4xx   | Client error. Improper requests (e.g., resource missing or bad format). |
| 5xx   | Server error. Server failed to process the request. |

### Common HTTP Status Codes

| Code  | Description |
|-------|-------------|
| 200 OK        | Request successful; response body contains requested resource. |
| 302 Found     | Redirects client to another URL (e.g., after login). |
| 400 Bad Request | Malformed request (e.g., missing line terminators). |
| 403 Forbidden  | Client lacks permission, or server detected malicious input. |
| 404 Not Found  | Requested resource does not exist. |
| 500 Internal Server Error | Server cannot process the request. |

**Note:** Some servers (Cloudflare, AWS) implement custom codes. For a full list of HTTP methods and codes, refer to official documentation.


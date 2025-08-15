# HTTP Headers - Summary

HTTP headers are key-value pairs passed between clients and servers to provide additional context about the request or response. They are categorized as:

- **General Headers**
- **Entity Headers**
- **Request Headers**
- **Response Headers**
- **Security Headers**

## General Headers

Used in both requests and responses to describe the message rather than its content.

| Header     | Example                             | Description                                                         |
| ---------- | ----------------------------------- | ------------------------------------------------------------------- |
| Date       | Date: Wed, 16 Feb 2022 10:38:44 GMT | Time message originated (UTC preferred)                             |
| Connection | Connection: close                   | Indicates if connection should stay alive (`close` or `keep-alive`) |

## Entity Headers

Describe the content (entity) transferred.

| Header           | Example                     | Description                                     |
| ---------------- | --------------------------- | ----------------------------------------------- |
| Content-Type     | Content-Type: text/html     | Type of resource; charset denotes encoding      |
| Media-Type       | Media-Type: application/pdf | Similar to Content-Type; can include charset    |
| Boundary         | boundary="b4e4fbd93540"     | Separates multiple contents in the same message |
| Content-Length   | Content-Length: 385         | Size of the entity                              |
| Content-Encoding | Content-Encoding: gzip      | Encoding transformations like compression       |

## Request Headers

Sent by the client in a request, unrelated to content.

| Header        | Example                                                                 | Description                   |
| ------------- | ----------------------------------------------------------------------- | ----------------------------- |
| Host          | Host: [www.inlanefreight.com](http://www.inlanefreight.com)             | Target server host or IP      |
| User-Agent    | User-Agent: curl/7.77.0                                                 | Client info (browser, OS)     |
| Referer       | Referer: [http://www.inlanefreight.com/](http://www.inlanefreight.com/) | Source URL of request         |
| Accept        | Accept: */*                                                             | Media types client can handle |
| Cookie        | Cookie: PHPSESSID=b4e4fbd93540                                          | Client-side data identifier   |
| Authorization | Authorization: BASIC cGFzc3dvcmQK                                       | Token-based authentication    |

## Response Headers

Sent by the server in a response, unrelated to content.

| Header           | Example                                   | Description                       |
| ---------------- | ----------------------------------------- | --------------------------------- |
| Server           | Server: Apache/2.2.14 (Win32)             | Server software information       |
| Set-Cookie       | Set-Cookie: PHPSESSID=b4e4fbd93540        | Cookies for client identification |
| WWW-Authenticate | WWW-Authenticate: BASIC realm="localhost" | Type of authentication required   |

## Security Headers

Enhance browser security.

| Header                    | Example                                     | Description                               |
| ------------------------- | ------------------------------------------- | ----------------------------------------- |
| Content-Security-Policy   | Content-Security-Policy: script-src 'self'  | Restricts resource sources (prevents XSS) |
| Strict-Transport-Security | Strict-Transport-Security: max-age=31536000 | Forces HTTPS usage                        |
| Referrer-Policy           | Referrer-Policy: origin                     | Controls Referer header exposure          |

## cURL Examples

- `-v`: verbose, shows full request/response
- `-I`: HEAD request, shows only response headers
- `-i`: shows headers and body
- `-H`: set custom headers
- `-A`: set User-Agent

```bash
curl -I https://www.inlanefreight.com
curl https://www.inlanefreight.com -A 'Mozilla/5.0'
```

## Browser DevTools

- Network tab shows requests.
- Click requests to view HTTP headers.
- `Headers` tab shows request/response headers; `Raw` button displays original format.
- `Cookies` tab shows cookies in use.


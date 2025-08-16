# HTTP GET, Basic Auth, and Parameters: Learning Guide

## GET Requests
- Browsers default to GET when visiting a URL.
- GET requests retrieve resources from the server.
- Subsequent requests may use other HTTP methods.
- Network tab in browser devtools shows all HTTP requests.

**Exercise:** Visit a website, monitor the Network tab, and observe how the page communicates with the backend.

---

## HTTP Basic Authentication
- Basic Auth is handled directly by the webserver.
- Unlike normal login forms (POST requests), credentials are validated at the server level.
- Example credentials: `admin:admin`.
- Accessing a protected page with cURL:

```bash
curl -i http://<SERVER_IP>:<PORT>/
```
- Response:
```
HTTP/1.1 401 Authorization Required
WWW-Authenticate: Basic realm="Access denied"
Access denied
```

- Provide credentials via cURL:
```bash
curl -u admin:admin http://<SERVER_IP>:<PORT>/
```
- Alternative method via URL:
```bash
curl http://admin:admin@<SERVER_IP>:<PORT>/
```
- Browser access also works similarly.

---

## Authorization Header
- With `-v` flag in cURL, we see:
```bash
> Authorization: Basic YWRtaW46YWRtaW4=
```
- This value is Base64 encoded `username:password`.
- Modern authentication (e.g., JWT) uses `Bearer` tokens.
- We can manually set the Authorization header with `-H`:
```bash
curl -H 'Authorization: Basic YWRtaW46YWRtaW4=' http://<SERVER_IP>:<PORT>/
```
- This also grants access to the page.
- Most modern web apps use login forms with POST and cookies to maintain authentication.

---

## GET Parameters
- After authentication, pages may have search functions.
- Example: City Search returning cities matching input.
- GET parameters appear in the URL: `search.php?search=le`.
- Network tab shows the backend request.
- We can send the same request via cURL:
```bash
curl 'http://<SERVER_IP>:<PORT>/search.php?search=le' -H 'Authorization: Basic YWRtaW46YWRtaW4='
```
- Response:
```
Leeds (UK)
Leicester (UK)
```
- Browser devtools allow copying requests as cURL or Fetch commands for replay.
- Responses can be viewed in detail in the devtools, including headers and returned data.

---

**Exercise:** Try sending GET requests with parameters, observe the headers and responses, and replay the requests using cURL or Fetch in the browser.


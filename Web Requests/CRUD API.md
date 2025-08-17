# HTTP POST, Authentication, JSON, and CRUD APIs: Learning Guide

## POST Requests

- Used when web applications need to send user data or files.
- POST places parameters in the **HTTP request body**, unlike GET which uses the URL.

**Benefits of POST over GET:**

1. **Lack of Logging:** Avoids logging large data/files in URL.
2. **Less Encoding:** Body accepts binary data; fewer characters need encoding.
3. **More Data:** Can send larger amounts of data; URLs have length limits (\~2000 characters).

---

## Login Forms and POST

- Web apps often use POST for login forms instead of HTTP Basic Auth.
- Example POST data: `username=admin&password=admin`
- Can send via cURL:

```bash
curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/
```

- Use `-L` to follow redirects if the login redirects to another page.

---

## Authenticated Cookies

- Successful login returns a cookie (`Set-Cookie`) to maintain session.
- Use with cURL:

```bash
curl -b 'PHPSESSID=<cookie_value>' http://<SERVER_IP>:<PORT>/
```

- Can also be set via `-H 'Cookie: ...'` header.
- Browsers store cookies in Storage tab for persistent authentication.

---

## JSON Data in POST Requests

- Some POST requests send **JSON payloads**, e.g., `{"search":"London"}`.
- Requires `Content-Type: application/json` header.
- Replicate with cURL:

```bash
curl -X POST -d '{"search":"london"}' -b 'PHPSESSID=<cookie_value>' -H 'Content-Type: application/json' http://<SERVER_IP>:<PORT>/search.php
```

- Can also use Fetch in browser console for similar requests.

---

## CRUD APIs

- Many APIs interact with databases and support CRUD operations:

| Operation | HTTP Method | Description                                       |
| --------- | ----------- | ------------------------------------------------- |
| Create    | POST        | Adds new data to the database table               |
| Read      | GET         | Reads an entity from the database table           |
| Update    | PUT         | Updates the data of a database entry              |
| Delete    | DELETE      | Removes a specified entry from the database table |

- Example (Read city info):

```bash
curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq
```

- Example (Create new city):

```bash
curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```

- Example (Update city):

```bash
curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```

- Example (Delete city):

```bash
curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City
```

- Output is usually returned in **JSON format**, which can be piped to `jq` for better readability.

---


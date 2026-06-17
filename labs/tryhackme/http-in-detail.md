# 📡 HTTP in Detail — Notes

## 🎯 Objective

Understand how HTTP works as a communication protocol between a browser and a server, including:
- Requests and responses
- Methods
- Status codes
- Headers
- Cookies

---

# 🌐 What is HTTP?

HTTP (**HyperText Transfer Protocol**) is a set of rules used for communication between a client (browser) and a web server.

It is used to transfer:
- HTML
- Images
- Videos
- API data

---

# 🔐 What is HTTPS?

HTTPS is the secure version of HTTP.

## Key differences:
- Encrypts data in transit
- Prevents interception
- Verifies server identity

## Key idea:
HTTPS ensures communication is:
- Private
- Secure
- Trusted

---

# 🌍 What is a URL?

A URL defines how to access a resource on the internet.

Example:
```
http://user:password@tryhackme.com:80/view-room?id=1#task3
```

## Breakdown:

- **Scheme** → Protocol (HTTP, HTTPS, FTP)
- **User** → Optional login credentials
- **Host** → Domain or IP
- **Port** → Connection endpoint (80 / 443 default)
- **Path** → Resource location
- **Query String** → Extra parameters (`?id=1`)
- **Fragment** → Section of page (`#task3`)

---

# 📡 HTTP Methods

HTTP methods define the **intended action** of a request.

## Common methods:
- **GET** → Retrieve data
- **POST** → Send data / create resource
- **PUT** → Update resource
- **DELETE** → Remove resource

## Key idea:
Different methods = different actions on the same endpoint.

---

# 📊 HTTP Status Codes

When a server responds, the first line contains a status code.

## Status Code Ranges:

- **100–199** → Informational (request received, continue)
- **200–299** → Success
- **300–399** → Redirection
- **400–499** → Client errors
- **500–599** → Server errors

---

## Common Status Codes:

- **200 OK** → Request successful
- **201 Created** → Resource created
- **301 Moved Permanently** → Permanent redirect
- **302 Found** → Temporary redirect
- **400 Bad Request** → Invalid request
- **401 Unauthorized** → Authentication required
- **403 Forbidden** → No permission
- **404 Not Found** → Resource missing
- **405 Method Not Allowed** → Wrong HTTP method
- **500 Internal Server Error** → Server failure
- **503 Service Unavailable** → Server overloaded or down

---

# 📡 Example HTTP Request

```
GET / HTTP/1.1

Host: tryhackme.com
User-Agent: Firefox/87.0
Referer: https://tryhackme.com/
```

## Breakdown:
- Line 1 → Method + path + protocol version
- Line 2 → Target host
- Line 3 → Browser identity
- Line 4 → Previous page source
- Blank line → End of request

---

# 📥 Example HTTP Response

```
HTTP/1.1 200 OK

Server: nginx/1.15.8
Date: Fri, 09 Apr 2021 13:34:03 GMT
Content-Type: text/html
Content-Length: 98
<html>...</html>
```

## Breakdown

- Line 1 → Status + protocol version  
- Line 2 → Server software  
- Line 3 → Timestamp  
- Line 4 → Response type  
- Line 5 → Response size  
- Blank line → End of headers  
- Body → Actual content  

---

# 🧾 HTTP Headers

Headers are extra metadata sent with HTTP requests and responses.

---

## 📤 Common Request Headers

- **Host** → Target website  
- **User-Agent** → Browser information  
- **Content-Length** → Size of the request body  
- **Accept-Encoding** → Compression formats supported  
- **Cookie** → Stored client data sent to the server  

---

## 📥 Common Response Headers

- **Set-Cookie** → Stores a cookie in the browser  
- **Cache-Control** → Browser caching rules  
- **Content-Type** → Type of returned data (HTML, JSON, etc.)  
- **Content-Encoding** → Compression method used  

---

# 🍪 Cookies & Sessions

Cookies are small pieces of data stored in the browser.

## How cookies work

- Server sends a cookie using `Set-Cookie`  
- Browser stores it  
- Browser sends it back with every request  

---

## 🧠 Why cookies exist

HTTP is stateless, meaning it does not remember previous requests.

Cookies solve this by:

- Tracking sessions  
- Storing user identity tokens  
- Maintaining login state  

---

## 🔐 Common use cases

- Authentication (login sessions)  
- User preferences  
- Tracking activity  

Cookies usually store:

- Tokens (not passwords)  
- Unique identifiers  

---

## 👀 Viewing cookies

You can inspect cookies using browser DevTools:

- Open the **Network** tab  
- Select a request  
- Check the **Cookies** section  

---

# 🧠 Key Takeaways

- HTTP defines how web communication works  
- HTTPS adds encryption and trust  
- URLs define how to access resources  
- Methods define actions (GET, POST, etc.)  
- Status codes define outcomes  
- Headers add metadata  
- Cookies enable state in a stateless protocol  

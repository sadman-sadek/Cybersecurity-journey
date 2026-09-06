# How a Web Server Works

## What is a Web Server?

A web server is software and/or a server system that accepts HTTP/HTTPS requests from clients and returns appropriate responses.

A client is commonly a web browser.

Basic communication:

    Browser
       ↓
    HTTP Request
       ↓
    Web Server
       ↓
    HTTP Response
       ↓
    Browser

---

# Client and Server

## Client

A client requests a resource or service.

Example:

- Web browser
- Mobile application
- API client

## Server

A server receives requests and provides resources or services.

For web communication, a web server handles HTTP/HTTPS traffic.

---

# How a Web Request Works

Suppose the user enters:

    https://example.com

The browser needs to communicate with the server hosting the website.

A simplified process is:

    Browser
       ↓
    DNS Resolution
       ↓
    Server IP
       ↓
    TCP/TLS Connection
       ↓
    HTTP Request
       ↓
    Web Server
       ↓
    HTTP Response
       ↓
    Browser

---

# HTTP Request

An HTTP request tells the server what the client wants.

Example:

    GET /index.html HTTP/1.1
    Host: example.com

A request can contain:

- HTTP method
- Path
- Headers
- Cookies
- Request body

---

# HTTP Methods

Common HTTP methods include:

## GET

Used to request a resource.

Example:

    GET /index.html

## POST

Commonly used to submit data to a server.

Example:

    POST /login

Other methods include:

- PUT
- PATCH
- DELETE
- HEAD

---

# HTTP Response

The server sends an HTTP response back to the client.

Example:

    HTTP/1.1 200 OK
    Content-Type: text/html

The response may contain:

- Status code
- Headers
- Response body

---

# HTTP Status Codes

Status codes provide information about the result of a request.

### 2xx — Success

Example:

    200 OK

The request was successfully processed.

### 3xx — Redirection

Example:

    301
    302

The client is being redirected or the resource has another location.

### 4xx — Client Error

Examples:

    400 Bad Request
    401 Unauthorized
    403 Forbidden
    404 Not Found

These generally indicate a problem with the request or access.

### 5xx — Server Error

Examples:

    500 Internal Server Error
    502 Bad Gateway
    503 Service Unavailable

These generally indicate a server-side or upstream problem.

---

# Ports

Web services commonly use specific TCP ports.

    HTTP  → 80
    HTTPS → 443

A server application listens for incoming connections on a port.

Simplified:

    Client
       ↓
    IP Address + Port
       ↓
    Web Service

---

# Static Content

A web server can return files that already exist.

Example:

    Browser
       ↓
    Web Server
       ↓
    index.html
       ↓
    Browser

Other static resources can include:

- CSS
- JavaScript
- Images
- Fonts

---

# Dynamic Content

A server can also generate responses dynamically.

Example:

    Browser
       ↓
    Web Server
       ↓
    Application
       ↓
    Database
       ↓
    Application
       ↓
    Response
       ↓
    Browser

For example, when a user logs in, the application may verify the credentials against stored data and generate an appropriate response.

---

# Web Server vs Application Server

A web server and application are related but are not necessarily the same component.

A simplified architecture can be:

    Client
      ↓
    Web Server / Reverse Proxy
      ↓
    Application
      ↓
    Database

The web-facing server may handle HTTP connections and forward requests to the application.

The application handles business logic.

The database stores application data.

---

# Reverse Proxy

A reverse proxy sits between clients and backend servers.

Example:

    Client
       ↓
    Reverse Proxy
       ↓
    Application Server

A reverse proxy can provide functions such as:

- Request forwarding
- TLS termination
- Load balancing
- Access control
- Caching

---

# Web Server and Cybersecurity

Understanding web servers is essential for web security.

Security professionals need to understand:

- HTTP/HTTPS
- Requests
- Responses
- Headers
- Cookies
- Ports
- Authentication
- Sessions
- Server-side applications

Attackers may target:

- Web server software
- Web applications
- Misconfigurations
- Authentication mechanisms
- Exposed services

Understanding how a normal request works makes it easier to understand abnormal or malicious requests.

---

# Simple Example

Suppose a browser requests:

    GET /login HTTP/1.1

The request reaches the web-facing server.

The server may:

    Receive Request
          ↓
    Check Request
          ↓
    Serve Static Content
       OR
    Forward to Application
          ↓
    Application Processes Request
          ↓
    Response Generated
          ↓
    Response Sent to Browser

---

# Key Takeaway

A web server receives HTTP/HTTPS requests and sends responses.

The basic mechanism is:

    Client
      ↓
    Request
      ↓
    Web Server
      ↓
    Processing / Application
      ↓
    Response
      ↓
    Client

Static content can be served directly, while dynamic requests may involve an application and database.

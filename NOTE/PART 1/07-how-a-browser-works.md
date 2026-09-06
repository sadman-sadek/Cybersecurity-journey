# How a Browser Works

## What is a Browser?

A web browser is an application that allows users to access and interact with web resources.

Examples include:

- Chrome
- Firefox
- Edge
- Safari

A browser communicates with web servers using protocols such as HTTP and HTTPS and then processes the returned resources to display a webpage.

---

# Basic Browser Workflow

When a user enters:

    https://example.com

the simplified process is:

    URL
     ↓
    DNS Resolution
     ↓
    Network Connection
     ↓
    TLS (for HTTPS)
     ↓
    HTTP Request
     ↓
    Web Server
     ↓
    HTTP Response
     ↓
    HTML/CSS/JavaScript
     ↓
    Browser Processing
     ↓
    Rendering
     ↓
    Webpage

---

# Step 1 — URL

The user enters a URL such as:

    https://example.com

A URL can contain information such as:

- Scheme / protocol
- Domain name
- Port
- Path
- Query parameters
- Fragment

Example:

    https://example.com/products?id=10

---

# Step 2 — DNS Resolution

The browser needs the server's IP address.

DNS can resolve the domain name:

    example.com
         ↓
        DNS
         ↓
    IP Address

The browser or operating system may use cached DNS information to avoid performing the lookup again.

---

# Step 3 — Establishing a Connection

The browser establishes network communication with the destination.

For traditional HTTP/1.1 and HTTP/2 over TCP, this involves establishing a TCP connection.

For HTTPS, TLS is then used to provide encryption and authenticate the server.

Modern HTTP/3 uses QUIC instead of TCP, but the beginner-level concept remains:

    Browser
       ↓
    Secure Communication
       ↓
    Web Server

---

# Step 4 — HTTP Request

The browser sends an HTTP request to the server.

Example:

    GET / HTTP/1.1
    Host: example.com

The request may contain:

- HTTP method
- URL/path
- Headers
- Cookies
- Request body

---

# Step 5 — Server Response

The server returns an HTTP response.

Example:

    HTTP/1.1 200 OK
    Content-Type: text/html

The response can contain:

- Status code
- Headers
- HTML
- CSS
- JavaScript
- Images
- Other resources

---

# Step 6 — HTML Parsing

The browser receives HTML and parses it.

The HTML is converted into a structure called the:

**DOM — Document Object Model**

The DOM represents the structure of the webpage.

Example:

    HTML
      ↓
    DOM
      ↓
    Document Structure

---

# Step 7 — CSS Processing

The browser also processes CSS.

CSS describes how elements should look.

Examples:

- Color
- Font
- Size
- Position
- Layout

The browser creates a representation of the CSS rules, commonly referred to as the **CSSOM**.

---

# Step 8 — JavaScript Execution

JavaScript can be executed by the browser.

It can:

- Modify the DOM
- Respond to user actions
- Request data from servers
- Change page content
- Control application behavior

For example:

    User clicks button
          ↓
    JavaScript executes
          ↓
    DOM changes
          ↓
    Page updates

---

# Step 9 — Rendering

The browser combines information from HTML, CSS, and other resources to determine what should appear on the screen.

Simplified:

    HTML → DOM
    CSS  → CSSOM

    DOM + CSSOM
          ↓
    Rendering Process
          ↓
    Pixels on Screen

Modern browser rendering is more complex and may involve multiple stages such as layout, painting, and compositing.

---

# Browser and Additional Resources

A webpage often contains references to additional resources.

For example:

    HTML
     ↓
    CSS
    JavaScript
    Images
    Fonts

The browser may make additional HTTP requests to retrieve these resources.

Example:

    HTML
      ↓
    ┌───────┬──────────┬─────────┐
    CSS     JS       Images     Fonts
     ↓       ↓          ↓         ↓
              Browser
                 ↓
              Render

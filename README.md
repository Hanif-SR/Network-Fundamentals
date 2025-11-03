# 🚀 Computer Networks — OSI Model & HTTP (Quick Reference)

## What is a computer network? 🌐

A **computer network** is a collection of devices that communicate and share resources.

**Key concepts:**

* 🖥 **Host/Node:** Any device with an IP (PC, server, router).
* 📦 **Packet:** Unit of transmitted data.
* 📜 **Protocol:** Rules for communication.
* 🌐 **Topology:** Physical/logical layout of devices.

---

## Network models: OSI vs TCP/IP 🔄

* **OSI Model (7 layers):** Conceptual tool for understanding network responsibilities.
* **TCP/IP Model (4 layers):** Practical model powering the Internet.

💡 Many protocols map across both models.

---

## OSI 7-layer model — detailed 🏗️

| Layer                                                   | Role                              | Protocols / Examples                 |
| ------------------------------------------------------- | --------------------------------- | ------------------------------------ |
| <span style="color:#FF6F61">**7 - Application**</span>  | Network services to apps          | HTTP, HTTPS, FTP, SMTP, DNS, SSH     |
| <span style="color:#FFA500">**6 - Presentation**</span> | Encryption, encoding, compression | TLS/SSL, Base64, UTF-8               |
| <span style="color:#FFD700">**5 - Session**</span>      | Manage sessions & dialogues       | RPC sessions, NetBIOS                |
| <span style="color:#ADFF2F">**4 - Transport**</span>    | End-to-end delivery               | TCP, UDP, ports, segmentation        |
| <span style="color:#40E0D0">**3 - Network**</span>      | Routing & logical addressing      | IPv4, IPv6, ICMP                     |
| <span style="color:#6495ED">**2 - Data Link**</span>    | Node-to-node delivery             | Ethernet, Wi-Fi, ARP, MAC addresses  |
| <span style="color:#8A2BE2">**1 - Physical**</span>     | Physical media                    | Ethernet cables, fiber, RF, voltages |

---

## Application-layer protocols overview 📡

* **HTTP(S):** web resources
* **DNS:** domain names
* **SMTP / POP3 / IMAP:** email
* **FTP / SFTP:** file transfer
* **SSH:** secure shell

> Each protocol defines **format, semantics, and ports**.

---

## HTTP — one of Application-layer protocol 💻

### Basics

* **Full name:** HyperText Transfer Protocol
* **Ports:** 80 (HTTP), 443 (HTTPS)
* **Stateless:** Each request/response is independent

### How it works ⚡

```
Client --TCP--> Server
   |             |
   <--HTTP Response--
```

1. TCP connection to server
2. Client sends HTTP request
3. Server responds with status + headers + body
4. Connection may close or persist

### Example Request

```http
GET /index.html HTTP/1.1
Host: example.com
User-Agent: curl/8.0
Accept: text/html
Connection: keep-alive
```

### Example Response

```http
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1254

<html> ... </html>
```

### Common Methods 🔑

* **GET, POST, PUT, PATCH, DELETE, HEAD, OPTIONS**

### Status Codes 🎨

* **2xx:** ✅ Success
* **3xx:** 🔁 Redirect
* **4xx:** ⚠️ Client error
* **5xx:** ❌ Server error

### HTTP/1.1 vs HTTP/2 vs HTTP/3

| Version  | Features                                         |
| -------- | ------------------------------------------------ |
| HTTP/1.1 | Text-based, persistent connections               |
| HTTP/2   | Binary, multiplexed streams, header compression  |
| HTTP/3   | QUIC/UDP, faster handshake, better loss recovery |

### HTTPS & TLS 🔒

* HTTP + TLS = secure web communication
* Certificates authenticate servers; TLS encrypts traffic

---

## Practical tools & commands 🛠️

* **curl** — make HTTP requests
* **wget** — download resources
* **telnet / nc** — raw request testing
* **openssl s_client** — TLS inspection
* **Wireshark / tcpdump** — packet capture
* **Postman / Insomnia** — API dev
* **nmap** — network scanning

---

## Security considerations 🔐

* Use **HTTPS** always
* Enable **HSTS**
* Validate input & encode output
* Protect cookies with `Secure` & `HttpOnly`
* Rate-limit APIs
* Use modern TLS configurations
* Apply **CSP** to mitigate XSS

---

## Further Reading & Resources 📖

* [RFCs for HTTP and TLS](https://www.rfc-editor.org/)
* Official docs: **curl, Wireshark, Apache, Nginx**
* Tutorials on REST APIs & HTTP/2, HTTP/3

---

## Quick Reference Cheat-Sheet 📝

**Ports**

* HTTP: `80`
* HTTPS: `443`
* SSH: `22`
* DNS: `53`

**curl examples**

```bash
curl -i -H "Accept: application/json" https://api.example.com/resource
curl -X POST -H "Content-Type: application/json" -d '{"name":"test"}' https://api.example.com/items
```

**Telnet raw request**

```
$ telnet example.com 80
GET / HTTP/1.1
Host: example.com
(press Enter twice)
```

---

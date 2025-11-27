**HTTP – HTTPS – DNS - FTP**

Ø **HTTP (Hypertext Transfer Protocol)**

**Purpose:**

HTTP is the foundation of data communication on the **World Wide Web**. It defines how messages are **formatted and transmitted** between web clients (browsers) and web servers.

**Usage Scenarios:**

- Accessing websites (e.g., when you visit [http://example.com](http://example.com/)).
- Loading web pages, images, and other media.
- Transferring data between web applications and APIs (e.g., RESTful APIs).
- Web crawlers fetching pages for indexing.

**Key Features:**

- Operates on **port 80** by default.
- Uses a **request-response model** (client sends a request; server sends a response).
- **Stateless** — each request is independent and not linked to previous ones.
- Data is **not encrypted**, making it vulnerable to interception.

---

**2. HTTPS (Hypertext Transfer Protocol Secure)**

**Purpose**

HTTPS is the secure version of HTTP. It uses **TLS (Transport Layer Security)** or **SSL (Secure Sockets Layer)** to encrypt data exchanged between client and server, ensuring privacy and integrity.

**TLS/SSL CONNECTION**

v **Handshake Phase:

- *When a client connects to a server, they begin a "handshake" to establish trust. The server sends a digital certificate (issued by a trusted Certificate Authority), proving its identity.

v **Authentication & Key Exchange:

- *The client verifies the certificate. If it's valid, both parties agree on a session key, which is used to encrypt the data.

v **Secure Communication:

- *Once the handshake is done, all data exchanged between the client and server is encrypted. This means anyone who tries to intercept the data will see only scrambled information.

v **Connection Closure:

- *After the session ends, both sides discard the session key to maintain security.

**Usage Scenarios:**

- Online banking, shopping, and secure login pages.
- Any website handling sensitive information (passwords, personal data).
- APIs that require secure data exchange.
- E-commerce and payment gateways (e.g., PayPal, Stripe).

**Key Features:**

- Operates on **port 443** by default.
- Encrypts communication to prevent tampering.
- Authenticates the server’s identity using **digital certificates**.
- Widely used to meet privacy standards (e.g., GDPR, PCI DSS).

---

**3. DNS (Domain Name System)**

**Purpose:**

DNS translates **human-readable domain names** (like www.google.com) into **IP addresses** (like 142.250.190.14), which computers use to locate each other on a network.

**Usage Scenarios:**

- Resolving domain names when accessing websites.
- Email routing (using MX records).
- Load balancing and content delivery networks (CDNs) via DNS records.
- Network troubleshooting and diagnostics (using tools like nslookup or dig).

**Key Features:**

- Operates primarily on **port 53** (UDP for queries, TCP for zone transfers).
- Hierarchical structure (root servers → TLD servers → authoritative servers).
- Caches results to reduce lookup time.
- Essential for virtually all internet communication.

---

Ø **FTP (File Transfer Protocol)**

**Purpose:**

FTP is used for **transferring files** between a client and a server over a network. It allows users to upload, download, and manage files remotely.

**Usage Scenarios:**

- Uploading website files to a web hosting server.
- Downloading large datasets or software packages.
- Backing up and sharing files between systems.
- Legacy systems still using FTP for automated file exchange.

**Key Features:**

·       **Port 21** is used for the **control connection**. This is where commands like login, change directory, or list files are sent.

·       **Port 20** is used for the **data connection** in **active mode**. This is where actual file data is transferred.

·       Supports **active** and **passive** modes for data connection management.

o   **Active mode**: Server connects to client.

o   **Passive mode**: Client connects to server.

·       Basic authentication (username and password).

·       Data is transferred in **plain text**, so **FTPS** or **SFTP** is recommended for secure transfers.

o   **FTPS (File Transfer Protocol Secure)** is a secure version of FTP that uses SSL or TLS to encrypt data and protect login details during file transfers.

**FTPS**: Uses **Port 21**

o   **SFTP (SSH File Transfer Protocol)** is a secure file transfer protocol that runs over SSH (Secure Shell) and encrypts both commands and data.

It uses **Port 22** by default

---

**Summary Table**

| **Protocol** | **Full Name** | **Default Port** | **Purpose** | **Security** | **Common Use** |
| --- | --- | --- | --- | --- | --- |
| **HTTP** | Hypertext Transfer Protocol | 80 | Web browsing & data transfer | Unencrypted | Standard web traffic |
| **HTTPS** | Hypertext Transfer Protocol Secure | 443 | Secure web communication | Encrypted (TLS/SSL) | Secure websites, e-commerce |
| **DNS** | Domain Name System | 53 | Translate domain names to IPs | Limited (DNSSEC optional) | Domain resolution |
| **FTP** | File Transfer Protocol | 21 | File upload/download | Unencrypted | File sharing, website maintenance |

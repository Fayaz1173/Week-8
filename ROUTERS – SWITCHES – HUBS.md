**ROUTERS – SWITCHES – HUBS**

---

Ø **Routers**

v **Functionality**

A **router** is a network device that **connects multiple networks and directs data packets between them**. It determines the **best path** for data to travel from source to destination using routing tables and protocols (e.g., OSPF, BGP, RIP).

v **Key Functions:**

- Connects **LANs** (Local Area Networks) to **WANs** (Wide Area Networks), such as the internet.
- Uses **IP addresses** to route data between networks.
- Supports **Network Address Translation (NAT)**, allowing multiple devices to share one public IP address.
- Can include a **firewall**, **VPN**, and **access control features** for security.

v **Role in Network Security:**

- Acts as the **first line of defence** between internal and external networks.
- Filters incoming and outgoing traffic using **Access Control Lists (ACLs)**.
- Masks internal IPs using **NAT**, reducing exposure to attacks.
- Can implement **intrusion detection** and **traffic monitoring**.

---

Ø **Switches**

v **Functionality:**

A **switch** operates at the **Data Link Layer (Layer 2)** of the OSI model and is used to **connect multiple devices** (computers, printers, etc.) **within the same LAN**. It forwards data frames based on **MAC addresses**.

v **Key Functions:**

- Creates a **dedicated communication path** between sender and receiver, reducing data collisions.
- Maintains a **MAC address table** to direct traffic efficiently.
- Supports **VLANs (Virtual LANs)** to segment networks for better management and security.
- Operates at **Layer 2**, though some advanced switches (Layer 3 switches) also perform routing.

v **Role in Network Security:**

- **VLAN segmentation** isolates departments or users, limiting internal attack spread.
- **Port security** restricts which devices can connect based on MAC addresses.
- Can detect and mitigate **MAC flooding** or **ARP spoofing** attacks.
- Managed switches allow **traffic monitoring** and **security policy enforcement**.

**MAC flooding** is a network attack where someone sends a lot of fake MAC addresses to a switch.

This **overloads the switch’s MAC table**

---

Ø **Hubs**

v **Functionality**

A **hub** is a basic networking device that operates at the **Physical Layer (Layer 1)** of the OSI model. It simply broadcasts data it receives to **all connected devices**, regardless of the destination.

v **Key Functions**

- Connects multiple Ethernet devices in a simple network.
- Transmits signals (not packets) to all ports.
- Does not store or filter data — every connected device receives the same traffic.
- Mainly used in small or legacy networks.

v **Role in Network Security**

- **No built-in security features** — it cannot filter or restrict traffic.
- All data is broadcast to every device, making **packet sniffing** easy for attackers.
- Vulnerable to **eavesdropping** and **man-in-the-middle attacks**.
- Generally considered **obsolete** in modern secure networks.

---

v **Comparison of Security Implications**

| **Device** | **OSI Layer** | **Primary Function** | **Security Features** | **Security Risks** | **Overall Security Level** |
| --- | --- | --- | --- | --- | --- |
| **Router** | Layer 3 (Network) | Connects networks and routes data | NAT, ACLs, firewalls, VPN support | Misconfiguration can expose internal networks; firmware exploits | **High** — strong protection at the network boundary |
| **Switch** | Layer 2 (Data Link) | Connects devices within a LAN | VLANs, port security, traffic monitoring | Susceptible to MAC flooding or ARP spoofing if unmanaged | **Medium to High** — good internal network security if managed |
| **Hub** | Layer 1 (Physical) | Connects multiple Ethernet devices | None | Broadcasts all traffic; easy to intercept; no access control | **Low** — insecure and outdated |

---

**Summary**

- **Routers** provide **network segmentation** and **internet security** through routing and filtering.
- **Switches** enhance **LAN efficiency** and **internal segmentation** using VLANs and port controls.
- **Hubs** offer **no security** and should be replaced with switches in modern networks.

Together, routers and switches form the backbone of secure network infrastructures, while hubs are generally avoided due to their vulnerabilities.

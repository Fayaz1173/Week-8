# **Security Comparison: Routers vs Switches vs Hubs**

---
<img width="426" height="468" alt="image" src="https://github.com/user-attachments/assets/9e083a37-5db4-47ae-9b0c-f8532a77f044" />
<img width="891" height="672" alt="image" src="https://github.com/user-attachments/assets/d0b4f339-7ba7-4c7e-9f38-753b5158a334" />

# **1. Routers – Security Implications**

### **Strengths**

- **Network Boundary Protection:**
    
    Routers sit at Layer 3 and separate internal networks from external networks (e.g., the internet).
    
- **Traffic Filtering (ACLs):**
    
    Can explicitly permit or deny traffic based on IP, protocol, or port.
    
- **NAT (Network Address Translation):**
    
    Masks internal IP addresses, reducing exposure.
    
- **Integrated Security Tools:**
    
    Many routers include firewalls, VPN endpoints, DHCP snooping, and intrusion detection.
    

### **Risks / Weaknesses**

- **Misconfiguration:**
    
    Incorrect ACLs, open ports, or poorly implemented NAT can expose internal hosts.
    
- **Router Firmware Vulnerabilities:**
    
    Outdated firmware may allow remote exploitation.
    
- **Single Point of Failure:**
    
    If compromised, entire network boundaries collapse.
    

### **Overall Security Level:** **High**

Routers provide the most robust security functions at the network edge.

---

# **2. Switches – Security Implications**

### **Strengths**

- **VLAN Segmentation:**
    
    Reduces the spread of internal attacks by isolating departments/traffic.
    
- **Port Security:**
    
    Allows limiting connections by MAC address, preventing unauthorized device access.
    
- **Advanced Features:**
    
    Managed switches support storm control, DHCP snooping, ARP inspection, and traffic monitoring.
    

### **Risks / Weaknesses**

- **MAC Flooding Attacks:**
    
    Overloads the CAM table, forcing the switch to broadcast frames like a hub.
    
- **ARP Spoofing / Poisoning:**
    
    Attackers can redirect traffic unless protection (DAI, ARP inspection) is enabled.
    
- **Unmanaged Switches:**
    
    Offer no VLANs, no security controls, and behave closer to hubs.
    

### **Overall Security Level:** **Medium to High**

Strong inside the LAN **only when properly configured** and managed.

---

# **3. Hubs – Security Implications**

### **Strengths**

- None from a security perspective.Hubs are **Layer 1 repeaters** with **no intelligence**.

### **Risks / Weaknesses**

- **Broadcasts All Traffic:**
    
    Every device sees all frames → enables easy sniffing (eavesdropping).
    
- **Zero Filtering / Access Control:**
    
    Cannot block, isolate, or inspect traffic.
    
- **Highly Vulnerable to MITM Attacks:**
    
    Attackers can capture or manipulate all traffic with simple tools.
    
- **Obsolete:**
    
    Rarely used in modern networks due to inherent insecurity.
    

### **Overall Security Level:** **Low**

Hubs introduce significant risk and should be replaced with switches.

---

# **4. Direct Comparison of Security Implications**
<img width="1024" height="576" alt="image" src="https://github.com/user-attachments/assets/8b66c261-70d4-4aeb-af19-4827103f8c2c" />
<img width="1200" height="700" alt="image" src="https://github.com/user-attachments/assets/3a951651-ac81-4eb5-bf49-bbcc7f8b1ee1" />


| Device | Security Strengths | Security Risks | Typical OSI Layer | Security Level |
| --- | --- | --- | --- | --- |
| **Router** | ACLs, NAT, firewall/VPN support, segmentation | Misconfigurations, firmware exploits | Layer 3 | **High** |
| **Switch** | VLANs, port security, ARP inspection, monitoring | MAC flooding, ARP spoofing, weak default configs | Layer 2 (sometimes L3) | **Medium–High** |
| **Hub** | None | Total traffic exposure, sniffing, MITM attacks | Layer 1 | **Low** |

---

# **5. Key Observations (Concise)**

1. **Routers provide the strongest security** because they control traffic between networks and enforce boundary protection.
2. **Switches secure internal LANs** through segmentation and port-based controls—but must be *managed* to resist attacks.
3. **Hubs are inherently insecure**, broadcasting all traffic and offering no protection or filtering.

---

# **6. Final Summary**

- **Routers** act as the security perimeter, filtering traffic and hiding internal devices.
- **Switches** improve internal security with VLANs and port security but require configuration.
- **Hubs** offer no protection, expose all traffic, and should not be used in secure networks.
- In modern architectures, **a router + managed switches** form a secure infrastructure, while hubs are avoided entirely.

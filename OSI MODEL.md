OSI MODEL

v What is OSI Model (Open System Interconnection)



The OSI Model is a conceptual framework that standardizes how different networking systems communicate with one another. It divides the communication process into 7 layers, each with specific roles and functions.



v Purpose of the OSI model

·        To standardize network communication so devices from different vendors can work together.

·        To simplify troubleshooting by isolating issues to a specific layer.

·        To help understand how data moves from one system to another.

·        To enable modular design, meaning each layer can be developed or replaced independently.

v The 7 Layers of the OSI Model

§  Application Layer

§  Presentation Layer

§  Session Layer

§  Transport Layer

§  Network Layer

§  Data Link Layer

§  Physical Layer

Physical Layer (Layer 1 of the OSI Model)



v Position

Lowest layer of the OSI model, below the Data Link Layer.
Converts data (bits) into physical signals for transmission and vice versa.



v Core functionalities and responsibilities

Bit-to-Signal Conversion:

o   Turns bits into physical signals (electrical, light, or radio) for transmission.

o   Converts received signals back into bits.



Physical Media & Devices:

o   It is the layer that deals with hardware like cables and connectors.

o   Media: Twisted-pair, Coaxial, Optical fibre.

o   Connectors: UTP, BNC, MGRT.



Physical Topology: Defines how devices are physically connected.



o   Types of topologies: Star, Mesh, Bus.



o   Links Configuration:

§  Point-to-Point: A direct link connecting one sender and one receiver, as is common in a Mesh topology.

§  Multipoint:  A shared link where multiple devices or users communicate over the same medium, characteristic of a Bus topology

Hardware Operators:

o   Repeaters: Boost weak signals, by extending the viable length of a network segment.

o   Hubs: Broadcast signals to multiple devices.



Transmission Modes:

o   Simplex: One-way only.

o   Half-Duplex: Two-way, one at a time.

o   Full-Duplex: Two-way, simultaneously.



Encoding & Signalling:

o   Defines how bits are represented as signals.

o   Conversions:

§  Digital ↔ Digital

§  Digital ↔ Analog

§  Analog ↔ Digital

§  Analog ↔ Analog

o   Signal properties: Frequency, Amplitude, Wavelength.



v Examples And Protocols

IEEE 802.3 (Ethernet), IEEE 802.11 (Wi-Fi), Bluetooth (IEEE 802.15.1), Cellular(4g,5g)



Ø Security weaknesses (conceptual)

·       Lack of Built-In Security - The physical layer only handles bit transmission, it has no mechanisms for encryption, authentication, or integrity checking**.**

·       Wiretapping - Signals (electrical, optical, or radio) can be intercepted without direct contact**.**

·       Hardware Tampering - Physical manipulation or alteration of a device’s components

·       Device Spoofing and Impersonation - Digital or logical impersonation of a legitimate device

·       No Intrusion Detection at Physical Layer - The physical layer cannot distinguish between legitimate and malicious signal patterns.



Ø Defences:

·        Physical security - Locked closets, Port locks

·        Use Fiber where possible - Harder to tap

·        Encryption at higher layers - Even if attackers manage to intercept signals at the physical layer, encryption at upper layers ensures they can’t read the actual data.



DATA LINK LAYER



The Data Link Layer (Layer 2) in the OSI model ensures reliable data transfer between directly connected nodes—a process called nod-to-nod delivery. It also prepares data from the Network Layer for transmission over the Physical Layer and handles flow, error, and access control locally between devices.



1. Position and Core Principle

Location: Between the Network (Layer 3) and Physical (Layer 1) layers.
Main Role: Transfers frames from one node to the next, not across the whole network.
Example: Data goes from Host A → Router 1 → Router 2 → Host B. Each step is a “hop.”



2. Key Functions



v Flow Control

Regulates data speed between two connected nodes.
Prevents buffer overflow by ensuring the receiver isn’t overloaded.
Uses protocols like Stop-and-Wait, Go-Back-N, and Selective Repeat.



v Error Control

Detects and corrects errors in each transmission link.
Uses CRC (Cyclic Redundancy Check).
Errors are fixed nod-by-nod for faster recovery.



v Access Control

Manages which device can transmit on a shared network medium.
Prevents collisions using methods like CSMA/CD, Aloha, and Token Ring.



v Physical Addressing

Uses 48-bit MAC addresses to identify devices within the same network.
MAC addresses work locally and it is fixed; IP addresses are used across networks.



v Framing

Breaks packets from the Network Layer into frames with headers and trailers.
These add control information for reliable delivery to the next hop.





Network Layer – Core Responsibilities (Layer 3)



Overview



The Network Layer ensures host-to-host delivery of data across multiple networks.
It uses logical addressing (IP addresses) and routing to move packets from the source to the destination.



Main Functions





Routing

o   Determines the best path for packets to travel.

o   Routers perform this function using routing tables and algorithms.

o   Protocols: RIP (Distance Vector), OSPF (Link State).





Fragmentation

o   Breaks large packets into smaller fragments to fit network limits (e.g., Ethernet’s 1500-byte MTU).

o   Each fragment is sent separately and reassembled at the destination.



Congestion Control

o   Manages network overload and data flow.

o   Mostly handled by the Transport Layer, but Network Layer uses:

§  ICMP, IGMP for signalling

§  Leaky Bucket / Token Bucket algorithms





Protocol	Full Name	Purpose	Layer	Type of Signaling
ICMP	Internet Control Message Protocol	Reports errors, tests connectivity	Network (Layer 3)	Control / Error signaling
IGMP	Internet Group Management Protocol	Manages multicast group membership	Network (Layer 3)	Multicast membership signaling





The Transport Layer: Summary



The Transport Layer is the 4th layer of the OSI model. It sits between the Application Layer and the Network Layer, ensuring end-to-end delivery of data between applications on different devices using port numbers.



Main Functions



End-to-End Delivery: Sends data from one application to another using port numbers (e.g., port 25 for email).
Segmentation: Breaks data from the Application Layer into smaller segments.
Multiplexing/De-multiplexing: Allows many apps to share the same network connection.
Error Control: Uses checksums to detect errors.
Flow Control: Prevents the sender from overwhelming the receiver.
Congestion Control: Prevents network overload.













Key Protocols



TCP (Transmission Control Protocol):



o   Reliable and connection-oriented

o   Guarantees no data loss and in-order delivery

o   Used in apps like web browsing (HTTP)



UDP (User Datagram Protocol):



o   Unreliable and connectionless

o   Faster but without delivery guarantees

o   Used for streaming, gaming, voice, etc.



Session Layer (Layer 5 of the OSI model)





The Session Layer (Layer 5 of the OSI model) which handles user authentication, authorization, session recovery, and synchronization for real-time communication.

Core Functions



Session Establishment
Authentication: Verifies the user’s identity (e.g., login using username and password).
Authorization: Grants specific privileges after authentication (e.g., allowing banking transactions but not server access).



EG: When you visit a bank’s login page, the server creates a session. You enter your credentials for authentication, and once verified, you access your account with specific permissions that's authorization.





Session Restoration (Checkpointing)
Saves session state so it can be resumed after interruption.
Enabled in apps like browsers (e.g., Firefox restores open tabs).
Disabled in secure apps like online banking to prevent hijacking.
Also used in large downloads to resume from the last checkpoint.
Uses session beans to save the state of the session



EG: If your computer shuts down and the browser offers to restore your tabs, it's because the browser saved your session data, allowing you to reopen the tabs you were using before.



EG: When downloading a large file, checkpoints split it into parts (e.g., every 100MB). If the download stops at 200MB, it can restart from there instead of starting over, thanks to these checkpoints.







Synchronization and Flow Control
Keeps audio, video, and subtitles in sync during real-time communication (e.g., webinars, streaming).
Prevents issues like lip-sync errors or delayed sound.

4.     Session and presentation layers are handled by applications, not the OS, because they deal with app-specific tasks like managing user sessions and formatting or encrypting data things that depend on the application's needs, not the operating system.



The Presentation Layer





The Presentation Layer (Layer 6 of the OSI model) acts as a translator between systems, ensuring data is readable by the receiving application regardless of format differences. It performs three main functions:





Core Functions and Implementation (Summary)



Code Conversion and Data Formatting – Converts data between different encoding formats (e.g., ASCII ↔ EBCDIC) so that applications on different systems can understand each other.





Encryption and Decryption – Secures data during transmission by converting plain text into cipher text (encryption) and back (decryption), protecting it from unauthorized access.





Data Compression – Reduces the size of data for faster and more efficient transmission, similar to zipping files.





Implementation:
These functions are handled by the application, not the operating system. Developers decide which features to include based on their app’s needs—some may use all, some none. For example, web browsers handle encryption when connecting to secure websites, not the OS.



In short:
The Presentation Layer ensures data is properly formatted, secure, and efficient for communication between applications





An Overview of Networking Layers, Protocols, and Devices



The OSI model divides computer networking into seven layers, each with specific roles, data formats, devices, and protocols. It ensures smooth data flow from one device to another, from physical transmission to user interaction.





1. Data Flow and Encapsulation

As data moves down the OSI layers, it gets wrapped with headers — a process called encapsulation.

Layer	 	Data Unit	Function
Application (7)	 	Data/Message	User interaction
Presentation (6)	 	Data	Formatting & encryption
Session (5)	 	Data	Managing sessions
Transport (4)	 	Segment	Reliable delivery
Network (3)	 	Packet	Routing via IP
Data Link (2)	 	Frame	Local transmission
Physical (1)	 	Bits	Electrical/optical signals
 

 

 	 	 	 



2. Devices by Layer



Layer 7–4 (Top Layers): Software-based

Gateway: Connects networks

Firewall: Security filtering

PCs/Phones: End-user devices



Layer 3 (Network):

Router: Forwards packets via IP

B-Router / L3 Switch: Routing + switching



Layer 2 (Data Link):

Switch, Bridge, NIC: Manage local data using MAC addresses



Layer 1 (Physical):

Hub, Repeater, Cables: Transmit raw bits





3. Key Protocols

Layer	Protocols	Function
Application (7)	HTTP, FTP, DNS, DHCP, SMTP, POP, Telnet	Web, email, and remote access
Presentation (6)	SSL/TLS, MIME	Encryption & data formatting
Session (5)	PPTP, NETBIOS	Authentication & client-server communication
Transport (4)	TCP, UDP	Reliable or fast data delivery
Network (3)	IP, ICMP, IGMP	Routing & error reporting
Data Link (2)	Ethernet, Wi-Fi, ARP, RARP	Local data transmission
Physical (1)	IEEE 802.3 / 802.11	Hardware standards



4. Connectivity Scope

Layer	Scope	Example
Transport	End-to-End	App ↔ App
Network	Source-to-Destination	Host ↔ Host
Data Link	Node-to-Node	Device ↔ Router
 	 	 



In short:
The OSI model organizes how data travels across a network — from physical signals (Layer 1) to user applications (Layer 7) — using defined devices, protocols, and encapsulation for efficient, secure communication.








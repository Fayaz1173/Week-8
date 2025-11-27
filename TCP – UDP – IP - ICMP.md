TCP – UDP – IP - ICMP



Ø TCP (Transmission Control Protocol)

Type: Connection-oriented
Function: Ensures reliable, ordered, and error-checked delivery of data between devices.

v KEY FEATURES

·       Reliable Delivery: Ensures all data sent is received by the recipient. If data is lost or corrupted, TCP resends it.

·       Connection-Oriented: A connection (or "session") must be established between sender and receiver before data transfer begins.

·       Ordered Data Transfer: Data packets are reassembled in the correct order at the receiving end.

·       Flow Control: Prevents the sender from overwhelming the receiver with too much data at once.

·       Error Detection: Uses checksums to detect errors in transmission.

v Used for:

·       Web browsing (HTTP/HTTPS)

·       Email (SMTP, IMAP, POP3)

·       File transfer (FTP)

Example: When you load a web page, TCP makes sure every piece of the page arrives correctly.

Ø UDP (User Datagram Protocol)

UDP (User Datagram Protocol) is a connection less protocol, used for time-sensitive transmissions where speed is more critical than reliability



v KEY FEATURES

·       Connectionless: No formal connection is established before sending data.

·       Unreliable Delivery: Does not guarantee packet delivery, order, or duplication protection. Lost packets are not resent.

·       Low Latency: Faster and more efficient than TCP because it skips the overhead of connection and error-checking.

·       No Congestion Control: Sends data as fast as the application allows, making it ideal for real-time services.9



v Used for:

Video streaming, online gaming, VoIP (calls), DNS lookups.

Example: A live stream may lose a few frames, but playback continues smoothly — that’s UDP.

Ø IP (Internet Protocol)

It is a set of rules used to send data from one computer to another over the internet or a network

1.       Addressing
IP assigns unique addresses (IP addresses) to devices on a network. These addresses help in identifying the source and destination of data packets.



2.       Packetizing Data
When data is sent over the internet, IP splits it into smaller chunks called packets. Each packet travels independently to its destination.



3.       Routing:
IP determines the best path for packets to travel across interconnected networks to reach their destination, using routers.



4.       Fragmentation and Reassembly:
If a packet is too large for a network segment, IP can break it into smaller units and reassemble them at the destination.





v Versions of IP

·        IPv4 (Internet Protocol version 4):
The most widely used version, with 32-bit addresses (e.g., 192.168.1.1).

·        IPv6 (Internet Protocol version 6):
Developed to address the shortage of IPv4 addresses. Uses 128-bit addresses (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334),

v Relation to Other Protocols:

·        Usually used with TCP (Transmission Control Protocol) or UDP (User Datagram Protocol):

o   TCP/IP ensures reliable data delivery (used for web browsing, email).

o   UDP/IP offers faster, connectionless communication but without reliability checks (used for streaming, gaming).



Example: IP decides how a data packet travels across networks to reach another computer.

Ø ICMP (Internet Control Message Protocol)

ICMP (Internet Control Message Protocol) is a network tool used to send error messages and testing signals between devices on a network. It helps check if a device is reachable (like with ping) and reports problems with data delivery.

Type: Support protocol (used by IP)B

v KEY FEATURES OF ICMP

Error Reporting:
ICMP communicates issues like unreachable destinations, timeouts, or packet delivery failures back to the source device.

Diagnostics:
ICMP is used in tools like:

ping: Sends ICMP Echo Request messages and waits for Echo Reply to measure reachability and latency.

traceroute: Uses ICMP messages to trace the path packets take through networks.

Works with IP:
ICMP is carried within IP packets but is not used to transport user data. Instead, it reports issues or provides network information.



Used for:

Testing and troubleshooting network connectivity.



Example: When you use ping google.com, ICMP checks if Google’s server is reachable.













In summary



Protocol	Layer	Type	Purpose	Example Use
TCP	Transport	Connection-oriented	Reliable communication	Web, email
UDP	Transport	Connectionless	Fast, no reliability	Streaming, gaming
IP	Internet	Connectionless	Routing and addressing	Packet delivery
ICMP	Internet	Support	Error reporting, diagnostics	Ping, traceroute


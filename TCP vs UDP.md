TCP vs UDP


<img width="600" height="360" alt="image" src="https://github.com/user-attachments/assets/b60f0264-143d-44d0-8e75-765ac28f891c" />
<img width="768" height="1024" alt="image" src="https://github.com/user-attachments/assets/c50a8cd4-f211-41dc-a824-a89c18832780" />

1. Core Concept
TCP — Connection-Oriented

A connection must be established before data transfer.

Achieved using the 3-way handshake (SYN → SYN-ACK → ACK).

Focuses on reliability, ordered delivery, and correctness.

UDP — Connectionless

No handshake, no formal connection setup.

Sends data (datagrams) immediately.

Focuses on speed, minimal overhead, low latency.

2. Major Technical Differences
Feature	TCP	UDP
Type	Connection-oriented	Connectionless
Handshake	Yes, 3-way	None
Reliability	Guaranteed delivery (ACKs, retransmission)	No guarantee (best effort)
Ordering	Packets arrive in order	Packets may arrive out of order
Error Checking	Checksum + recovery	Checksum only (no recovery)
Speed	Slower due to overhead	Faster, minimal overhead
Flow Control	Yes (e.g., sliding window)	No
Congestion Control	Yes (e.g., TCP Reno, CUBIC)	No
Data Format	Stream-based	Message-based (datagrams)
Header Size	Larger (20–60 bytes)	Smaller (8 bytes)
3. Reliability & Ordering
TCP

Uses ACKs, sequence numbers, and retransmission.

Ensures every byte is delivered and in the correct order.

If packets drop → TCP resends them.

UDP

No recovery, no acknowledgment, no ordering.

Packet loss remains unnoticed by the protocol.

Applications must handle reliability if needed.

4. Performance Characteristics
TCP

More overhead → slower but accurate.

Suited for applications needing full data integrity.

UDP

Minimal overhead → low latency & high throughput.

Ideal for real-time transmissions or where some loss is acceptable.

5. Common Use Cases
TCP Use Cases (when accuracy matters)

Web browsing (HTTP/HTTPS)

File transfer (FTP, SFTP)

Emails (SMTP, IMAP, POP3)

Remote login (SSH)

UDP Use Cases (when speed matters)

Video/voice streaming (VoIP)

Online gaming

DNS queries

Live broadcasts

DHCP

6. When to Choose TCP vs UDP
Choose TCP if you need:

Reliability

Ordered data

No loss tolerated

Congestion management

A stable connection

Choose UDP if you need:

Speed

Low latency

Can tolerate loss

Real-time or multicast traffic

Lower protocol overhead

7. Summary in One Sentence

TCP prioritizes reliability and order through connection setup and checks, while UDP prioritizes speed and simplicity by sending datagrams without establishing a connection.

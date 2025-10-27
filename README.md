# Task 5: Wireshark Network Traffic Analysis

This repository contains the deliverables for the Elevate Labs Cybersecurity Internship Task 5.

## 🎯 Objective
The objective of this task was to capture live network packets and identify basic protocols and traffic types.

## 🛠️ Tools Used
* **Wireshark:** A free and open-source packet analyzer used for network troubleshooting and analysis.

---

## 📊 Protocol Analysis

This report details the analysis of the captured `.pcap` file. The following three protocols were identified:

### 1. DNS (Domain Name System)

> **Function:** Translates human-readable domain names (like `www.google.com`) into machine-readable IP addresses.

**Analysis of Packet #38:**

I identified packet number 38 as a clear example of a Domain Name System (DNS) query.

* **Source IP:** `10.19.129.158` (My Computer)
* **Destination IP:** `10.19.129.43` (DNS Server)
* **Packet Info:** Standard query for an "A" record for `www.google.com`.

This packet shows my computer asking the DNS server for the specific IPv4 address associated with Google's website. This query is the essential first step my system takes to establish a connection with a website.

---

### 2. TCP (Transmission Control Protocol)

> **Function:** Provides reliable, connection-oriented data transmission for applications like web browsing by establishing a stable connection before sending data.

**Analysis of the Three-Way Handshake (Packets #644, #646, #648):**

I identified a sequence of packets demonstrating the TCP three-way handshake, which establishes a reliable connection.

1.  **Packet #644 [SYN]:** My computer (`10.19.129.158`) sends a `SYN` (synchronize) packet to the server (`10.19.129.43`) to initiate a new connection.
2.  **Packet #646 [SYN, ACK]:** The server responds with a `SYN, ACK` packet. It acknowledges my initial request and sends its own synchronize request back.
3.  **Packet #648 [ACK]:** My computer completes the handshake by sending an `ACK` (acknowledgment) packet.

This three-step process confirms that the connection is successfully established from both sides, ensuring TCP's reliability.

---

### 3. HTTP (Hypertext Transfer Protocol)

> **Function:** Defines how data is transmitted over the internet and determines how web servers and browsers should respond to commands.

**Analysis of HTTP Request/Response (Packets #4248, #4253):**

I identified a clear example of an HTTP conversation, which demonstrates the fundamental request-response model of the web.

* **Packet #4248 (HTTP POST):** My computer (`10.19.129.158`) sent an `HTTP POST` request to the web server (`54.255.175.10`). This packet represents my browser asking the server for a resource or sending data to it.

* **Packet #4253 (HTTP 200 OK):** The server replied with a packet containing `HTTP/1.1 200 OK`. The "200 OK" is a standard status code confirming that my request was received and processed successfully.

Together, these two packets show a complete and successful web transaction.

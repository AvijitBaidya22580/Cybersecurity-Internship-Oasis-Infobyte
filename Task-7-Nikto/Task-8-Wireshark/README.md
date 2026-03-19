# 🦈 Advanced Network Traffic Analysis using Wireshark

![Wireshark Banner](screenshots/banner.png)

---

## 📌 Executive Summary

This project presents a **comprehensive analysis of real-world network traffic** captured using **Wireshark**, within a controlled lab environment powered by **DVWA (Damn Vulnerable Web Application)** and **XAMPP**.

The objective is to simulate realistic web traffic, capture it at the network level, and analyze how modern protocols such as **DNS, HTTP, TCP, QUIC, and TLS 1.3** operate in practice.

This case study highlights how **secure communication is established**, how **data flows across networks**, and how **encryption impacts visibility**, making it highly relevant for real-world cybersecurity analysis.

---

## 🎯 Objectives

* Capture live network packets using Wireshark
* Analyze DNS resolution and web traffic behavior
* Observe HTTP communication using DVWA
* Understand TCP handshake and session establishment
* Analyze encrypted traffic (TLS & QUIC)
* Evaluate security implications of captured traffic

---

## 🛠 Tools & Technologies Used

* **Wireshark** – Network packet analyzer
* **DVWA (Damn Vulnerable Web Application)** – Vulnerable web app for testing
* **XAMPP** – Local web server (Apache + MySQL)
* **Kali Linux** – Analysis environment
* **VS Code** – Documentation and project management
* **Web Browser** – Traffic generation

---

## 🌐 Network Environment

| Component          | Value                     |
| ------------------ | ------------------------- |
| Attacker Machine   | 10.0.2.15                 |
| Gateway            | 192.168.1.1               |
| Local Server       | XAMPP (Apache)            |
| Web Application    | DVWA                      |
| External Domain    | chatgpt.com               |
| Protocols Observed | DNS, HTTP, TCP, TLS, QUIC |

---

## 📸 Capture Evidence

### 🔹 Network Traffic Overview

![Wireshark Capture](screenshots/wireshark-capture.png)

### 🔹 Deep Packet Inspection (Advanced)

![Packet Detail](screenshots/wireshark-packet-detail.png)

---

## 🔍 Detailed Packet Analysis

### 1️⃣ DNS Resolution Phase

The communication begins with DNS queries to resolve domain names into IP addresses:

* Query Types: **A (IPv4), AAAA (IPv6)**
* DNS Server: `192.168.1.1`

Resolved IPs:

* `104.18.32.47`
* `172.64.155.209`

**Insight:**
DNS acts as the entry point of all web communication and can reveal metadata about user activity.

---

### 2️⃣ HTTP Traffic (DVWA - Local Testing)

When interacting with DVWA (hosted on XAMPP):

* HTTP requests and responses are transmitted in **plain text**
* User inputs (e.g., login credentials) can be captured

**Insight:**
Unlike HTTPS, HTTP traffic is **not encrypted**, making it vulnerable to interception and analysis.

---

### 3️⃣ QUIC Protocol (HTTP/3)

Observed traffic shows QUIC communication:

* Runs over UDP
* Includes Initial and Protected Payload packets

**Insight:**
QUIC reduces latency and improves performance but limits packet inspection due to encryption.

---

### 4️⃣ TCP Handshake

Standard 3-way handshake observed:

* SYN → SYN-ACK → ACK

**Insight:**
Ensures reliable communication before data transfer.

---

### 5️⃣ TLS 1.3 Encryption

Secure communication established using TLS:

* Client Hello
* Server Hello
* Encrypted Application Data

**Insight:**
After handshake, payload becomes unreadable, protecting sensitive data.

---

## 🔐 Security Analysis

* 🔓 DVWA over HTTP exposes sensitive data in plaintext
* 🔒 HTTPS traffic is encrypted using TLS 1.3
* 🌐 DNS queries expose domain-level metadata
* ⚡ QUIC enhances speed but reduces visibility
* 👁️ Attackers rely on misconfigured HTTP services for exploitation

---

## ⚠️ Key Observations

* Plain HTTP is highly insecure and easily exploitable
* Modern applications heavily rely on encrypted protocols
* Network analysis tools cannot inspect encrypted payloads without decryption
* Metadata (IP, DNS, timing) still provides valuable intelligence

---

## 📁 Project Structure

Task-8-Wireshark/
│── screenshots/
│   ├── wireshark-capture.png
│   └── wireshark-packet-detail.png
│
│── wireshark_capture.pcapng
│── README.md

---

## 🎥 Demonstration Workflow

1. Start XAMPP (Apache & MySQL)
2. Launch DVWA in browser
3. Start Wireshark capture on active interface
4. Perform actions (login, navigation, requests)
5. Apply filters:

   * `http`
   * `dns`
   * `tcp`
   * `tls`
   * `quic`
6. Analyze captured packets
7. Save capture file

---

## 🚀 Key Learning Outcomes

* Hands-on experience with packet sniffing
* Understanding of modern web protocols
* Ability to analyze encrypted vs unencrypted traffic
* Practical exposure to real-world cybersecurity scenarios
* Insight into web application vulnerabilities (DVWA)

---

## 🏁 Conclusion

This project demonstrates how network traffic behaves in both **secure (HTTPS)** and **insecure (HTTP)** environments.

By combining **DVWA, XAMPP, and Wireshark**, it provides a realistic simulation of how attackers and analysts observe network communication.

The findings emphasize the importance of:

* Encrypted communication
* Secure web configurations
* Continuous network monitoring

---

## 👨‍💻 Author

**Avijit Baidya**
Cybersecurity Enthusiast | Aspiring Security Engineer 🚀

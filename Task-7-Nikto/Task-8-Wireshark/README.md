# 🦈 Capture & Analyze Network Traffic using Wireshark

![Task 8 Banner](screenshots/banner.png)

---

## 📌 Executive Summary

This project demonstrates **real-time network traffic capture and deep packet analysis** using **Wireshark** in a controlled cybersecurity lab environment.

The analysis includes both:

* 🌐 **Local vulnerable web traffic (DVWA over HTTP via XAMPP)**
* 🔒 **Real-world encrypted traffic (HTTPS, TLS 1.3, QUIC)**

The objective is to understand how data flows across networks, how secure communication is established, and how attackers or analysts interpret network-level information.

---

## 🎯 Objectives

* Capture live network traffic using Wireshark
* Analyze DNS, HTTP, TCP, TLS, and QUIC protocols
* Understand plaintext vs encrypted communication
* Perform packet-level inspection and interpretation
* Simulate real-world traffic monitoring scenarios

---

## 🛠 Tools & Technologies

* **Wireshark** – Network packet analyzer
* **DVWA (Damn Vulnerable Web Application)** – Vulnerable test environment
* **XAMPP** – Apache + MySQL server for hosting DVWA
* **Kali Linux** – Network analysis platform
* **VS Code** – Documentation and project management
* **Web Browser** – Traffic generation

---

## 🌐 Network Environment

| Component          | Value                     |
| ------------------ | ------------------------- |
| Attacker Machine   | 10.0.2.15                 |
| Gateway            | 192.168.1.1               |
| Local Server       | XAMPP (Apache)            |
| Web App            | DVWA                      |
| External Domain    | chatgpt.com               |
| Protocols Observed | DNS, HTTP, TCP, TLS, QUIC |

---

## 📸 Capture Evidence

![Wireshark Capture](screenshots/wireshark-capture.png)

---

## 🔍 Packet Analysis

### 1️⃣ DNS Resolution

The communication begins with DNS queries:

* `A` and `AAAA` requests sent to DNS server
* Domain `chatgpt.com` resolved to:

  * `104.18.32.47`
  * `172.64.155.209`

📌 **Insight:**
DNS queries reveal user activity and target domains even in encrypted environments.

---

### 2️⃣ HTTP Traffic (DVWA – Vulnerable Environment)

* DVWA runs on **XAMPP (Apache) using HTTP**
* Requests and responses are transmitted in **plaintext**

📌 **Insight:**
Sensitive data (e.g., credentials) can be intercepted easily → **major security risk**

---

### 3️⃣ TCP Communication

Observed standard **3-way handshake**:

* SYN → SYN-ACK → ACK

📌 **Insight:**
Ensures reliable communication before data transfer.

---

### 4️⃣ TLS 1.3 Encryption

Secure sessions established over HTTPS:

* Client Hello
* Server Hello
* Encrypted Application Data

📌 **Insight:**
After handshake, packet payload becomes unreadable.

---

### 5️⃣ QUIC Protocol (HTTP/3)

Observed QUIC traffic:

* Runs over UDP
* Includes Initial + Protected Payload packets

📌 **Insight:**
QUIC improves performance but reduces deep packet visibility.

---

## 🔬 Deep Packet Inspection (Advanced)

![Packet Detail](screenshots/wireshark-packet-detail.png)

This view reveals:

* Ethernet Frame
* IP Header
* TCP Segment
* Raw Hexadecimal Data

📌 **Insight:**
Used in **digital forensics and advanced threat analysis**.

---

## 🔐 Security Analysis

* 🔓 HTTP traffic (DVWA) exposes sensitive data
* 🔒 HTTPS traffic is encrypted (TLS 1.3)
* 🌐 DNS leaks metadata (domains visited)
* ⚡ QUIC enhances speed but limits inspection
* 👁️ Attackers target insecure HTTP services

---

## ⚠️ Key Observations

* Plain HTTP is **highly vulnerable**
* Modern systems rely heavily on encryption
* Encrypted traffic hides payload but not metadata
* Network analysis still provides valuable intelligence

---

## 📁 Project Structure

Task-8-Wireshark/
│── screenshots/
│   ├── banner.png
│   ├── wireshark-capture.png
│   └── wireshark-packet-detail.png
│
│── wireshark_capture.pcapng
│── README.md

---

## 🎥 Demonstration Workflow

1. Start XAMPP (Apache + MySQL)
2. Launch DVWA in browser
3. Start Wireshark capture (`eth0`)
4. Perform actions (login, browsing, requests)
5. Apply filters:

   ```
   http
   dns
   tcp
   tls
   quic
   ```
6. Analyze packets
7. Save `.pcapng` file

---

## 🚀 Key Learning Outcomes

* Hands-on packet sniffing and analysis
* Understanding of modern network protocols
* Ability to differentiate secure vs insecure traffic
* Practical exposure to cybersecurity monitoring
* Real-world attack surface understanding

---

## 🏁 Conclusion

This project demonstrates how network traffic behaves across both **secure and insecure environments**.

By integrating **DVWA, XAMPP, and Wireshark**, it provides a realistic simulation of how:

* Attackers intercept insecure traffic
* Analysts monitor network behavior
* Encryption protects sensitive data

It reinforces the importance of:

* Secure communication (HTTPS)
* Network monitoring
* Vulnerability awareness

---

## 👨‍💻 Author

**Avijit Baidya**
Cybersecurity Enthusiast | Aspiring Security Engineer 🚀

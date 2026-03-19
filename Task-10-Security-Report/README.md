# 🔐 Network Security Assessment Report

<p align="center">
  <b>Comprehensive Security Analysis using Nmap & Wireshark</b>
</p>

---

## 👨‍💻 Author

**Avijit Baidya**

---

## 📌 Executive Summary

This report presents a **comprehensive network security assessment** conducted on a local test environment using **Nmap** and **Wireshark**.

The objective was to identify:

* Open ports and services
* Potential vulnerabilities
* Network communication behavior
* Security misconfigurations

The analysis reveals multiple security concerns, particularly related to **outdated services, exposed ports, and insecure communication channels**.

---

## 🎯 Scope of Assessment

* Target System: `192.168.1.5`
* Environment: Local lab (DVWA hosted on XAMPP)
* Tools Used:

  * Nmap
  * Wireshark

---

## 🛠 Methodology

### 1️⃣ Network Scanning (Nmap)

Performed using:

```bash
nmap -sV -sC -O 192.168.1.5
```

Objectives:

* Identify open ports
* Detect running services
* Determine OS and versions

---

### 2️⃣ Traffic Analysis (Wireshark)

* Captured live network traffic
* Applied filters:

  * `http`
  * `dns`
  * `tcp`
  * `tls`

Objectives:

* Analyze packet flow
* Detect insecure communication
* Observe protocol behavior

---

## 🔍 Nmap Scan Results

### 🟢 Open Ports Identified

| Port | Service | Description         |
| ---- | ------- | ------------------- |
| 80   | HTTP    | Web server (Apache) |
| 3306 | MySQL   | Database service    |

---

### ⚠️ Key Findings

* Apache server is running on port 80
* MySQL service exposed
* No HTTPS (port 443) detected
* Indicates **lack of encrypted communication**

---

## 📡 Wireshark Analysis

### Observed Traffic:

* DNS queries (domain resolution)
* HTTP requests (DVWA interaction)
* TCP handshake sequences
* TLS traffic (external sites)
* QUIC protocol activity

---

### 🔴 Critical Observation

* DVWA traffic over HTTP is **unencrypted**
* Sensitive data can be intercepted

---

### 🔒 Secure Traffic Observation

* External traffic uses:

  * TLS 1.3
  * QUIC

* Payload is encrypted → not readable

---

## 🔐 Security Vulnerabilities Identified

### 🚨 1. Unencrypted HTTP Communication

* Data transmitted in plaintext
* Vulnerable to packet sniffing

---

### 🚨 2. Open Ports Exposure

* Port 80 and 3306 accessible
* Increases attack surface

---

### 🚨 3. Outdated Software (from previous scan)

* Apache
* PHP
* OpenSSL

---

### 🚨 4. Lack of Security Headers

* Missing HTTP security configurations

---

## 📊 Risk Assessment

| Vulnerability        | Severity  |
| -------------------- | --------- |
| HTTP (No Encryption) | 🔴 High   |
| Open Ports Exposure  | 🟠 Medium |
| Outdated Software    | 🔴 High   |
| Misconfiguration     | 🟠 Medium |

---

## 🛡 Recommendations

* Enable HTTPS (SSL/TLS)
* Close unused ports
* Restrict MySQL access
* Update all software components
* Implement security headers
* Use firewall rules

---

## 📁 Deliverables

* `network_security_assessment.md`
* `nmap_results.txt`
* `wireshark_capture.pcap`

---

## 🎥 Demo Idea

* Run Nmap scan
* Capture traffic in Wireshark
* Show packet filtering
* Explain vulnerabilities

---

## 🏁 Conclusion

The assessment highlights that **basic misconfigurations and lack of encryption** can expose systems to significant security risks.

This project demonstrates the importance of:

* Secure communication
* Network monitoring
* Regular vulnerability assessments

---

## ⚠ Disclaimer

This assessment was conducted in a controlled lab environment for educational purposes only.

<p align="center">
  <img src="screenshots/banner.png" alt="Nikto Banner" width="100%"/>
</p>

<h1 align="center">🔐 Vulnerability Scanning with Nikto</h1>

<p align="center">
  <b>Web Server Security Assessment | DVWA Lab | Kali Linux</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Nikto-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Platform-DVWA-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Type-Vulnerability%20Scan-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge"/>
</p>

---

## 📖 Executive Summary

This project demonstrates a **comprehensive web server vulnerability assessment** performed using **Nikto** against a locally hosted DVWA environment.

The scan identified multiple **high-risk misconfigurations**, including:
- Missing critical security headers  
- Outdated server components  
- Information disclosure endpoints  
- Unsafe HTTP methods  

These findings highlight how improperly configured systems can expose sensitive data and become vulnerable to real-world attacks.

---

## 🎯 Objectives

- Perform automated vulnerability scanning using Nikto  
- Identify web server misconfigurations  
- Analyze real-world vulnerabilities  
- Document findings in a professional security report  

---

## 🛠️ Tools & Environment

| Component | Description |
|----------|------------|
| Kali Linux | Attacker machine |
| Nikto v2.6.0 | Web vulnerability scanner |
| DVWA | Vulnerable web application |
| XAMPP | Apache + MySQL + PHP stack |
| VS Code | Documentation |
| GitHub | Version control |

---

## 🌐 Target Information

| Parameter | Value |
|----------|------|
| Target IP | 192.168.1.5 |
| Protocol | HTTP |
| Port | 80 |
| Server | Apache/2.4.58 (Win64) |
| PHP Version | 8.0.30 |
| OpenSSL | 3.1.3 |

---

## ⚡ Scan Execution

```bash
nikto -h http://192.168.1.5 -o nikto_scan_results.txt
```

📌 **Scan Insights:**
- 8000+ requests performed  
- Multiple vulnerabilities detected  
- Target identified as Windows-based Apache server  

---

## 📸 Scan Evidence

<p align="center">
  <img src="screenshots/nikto-scan.png" width="90%">
</p>

---

## 🔍 Vulnerability Findings

### 🚨 1. Missing Security Headers

The application lacks essential HTTP headers:
- Content-Security-Policy (CSP)
- X-Content-Type-Options
- Strict-Transport-Security (HSTS)
- Referrer-Policy
- Permissions-Policy

🔴 **Impact:**
- Cross-Site Scripting (XSS)
- Data leakage
- MIME sniffing vulnerabilities  

---

### 🚨 2. Outdated Software Components

| Component | Version | Risk |
|----------|--------|------|
| Apache | 2.4.58 | High |
| PHP | 8.0.30 | High |
| OpenSSL | 3.1.3 | High |

🔴 **Impact:**
- Known CVEs exploitable  
- Potential Remote Code Execution  

---

### 🚨 3. HTTP TRACE Enabled

🔴 **Impact:**
- Vulnerable to **Cross-Site Tracing (XST)** attacks  

---

### 🚨 4. Directory Indexing Enabled

Accessible directories:
- `/img/`
- `/icons/`

🔴 **Impact:**
- Exposure of internal files  
- Information disclosure  

---

### 🚨 5. Sensitive Endpoints Exposed

- `/server-status`
- `/phpmyadmin`
- Apache default files

🔴 **Impact:**
- Server information leakage  
- Increased attack surface  

---

## 📊 Risk Assessment

| Vulnerability | Severity |
|--------------|--------|
| Missing Headers | 🔴 High |
| Outdated Software | 🔴 High |
| Information Disclosure | 🔴 High |
| HTTP TRACE | 🟠 Medium |
| Directory Indexing | 🟠 Medium |

---

## 🛡️ Security Recommendations

- Disable HTTP TRACE method  
- Implement security headers (CSP, HSTS, etc.)  
- Disable directory listing  
- Restrict `/phpmyadmin` access  
- Secure `/server-status`  
- Regularly update Apache, PHP, OpenSSL  

---

## 📁 Project Structure

```
Task-7-Nikto/
│
├── screenshots/
│   ├── banner.png
│   └── nikto-scan.png
│
├── nikto_scan_results.txt
└── README.md
```

---

## 📚 Key Learning Outcomes

- Practical experience with Nikto scanning  
- Understanding real-world web vulnerabilities  
- Identifying misconfigurations in servers  
- Writing professional security reports  

---

## ⚠️ Disclaimer

This project was conducted in a **controlled lab environment (DVWA)** for educational purposes only.  
No unauthorized systems were targeted.

---

## ⭐ Final Thoughts

This assessment demonstrates how **basic misconfigurations can lead to critical security risks**, reinforcing the importance of secure system configuration and continuous monitoring.

---

<p align="center">
  🔥 <b>Cybersecurity is not about tools — it's about understanding risk.</b>
</p>
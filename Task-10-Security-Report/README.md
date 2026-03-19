<p align="center">
  <img src="screenshots/banner.png" width="100%">
</p>

<h1 align="center">🔐 Network Security Assessment Report</h1>

<p align="center"><b>Nmap + Wireshark Analysis | DVWA Lab | Kali Linux</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/Tool-Nmap-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Tool-Wireshark-blue?style=for-the-badge">
  <img src="https://img.shields.io/badge/Platform-Kali_Linux-black?style=for-the-badge">
  <img src="https://img.shields.io/badge/Environment-DVWA-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Type-Network_Security-red?style=for-the-badge">
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge">
</p>

---

## 📌 Executive Summary

This project presents a **comprehensive network security assessment** using:

* 🔍 **Nmap** → Active scanning
* 📡 **Wireshark** → Traffic analysis

The analysis identifies **open ports, exposed services, insecure communication, and potential attack surfaces**.

---

## 🔍 Nmap Scan Evidence

<p align="center">
  <img src="screenshots/nmap-scan-1.png" width="48%">
  <img src="screenshots/nmap-scan-2.png" width="48%">
</p>

<p align="center"><i>Figure: Nmap scan showing open ports and services</i></p>

---

## 📡 Wireshark Traffic Capture

<p align="center">
  <img src="screenshots/wireshark-capture.png" width="85%">
</p>

<p align="center"><i>Figure: Captured traffic including DNS, TCP, TLS, and QUIC</i></p>

---

## 🚨 Key Findings

* 🔴 SMB (445) exposed → high risk
* 🔴 NetBIOS (139) enabled → vulnerable
* 🔴 MySQL (3306) accessible → data risk
* 🔴 HTTP (80) unencrypted → sniffing possible
* 🟡 Self-signed HTTPS → not trusted

---

## 🛠 Tools Used

* Nmap
* Wireshark
* Kali Linux
* DVWA
* XAMPP
* VS Code

---

## 📄 Detailed Report

👉 [View Full Security Assessment](network_security_assessment.md)

---

## ⚠ Disclaimer

This project was conducted in a controlled lab environment for educational purposes only.

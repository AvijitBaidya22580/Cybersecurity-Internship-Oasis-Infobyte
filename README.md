# 🔐 Task 3: SQL Injection using DVWA

## 👨‍💻 Author

**Avijit Baidya**

---

## 🎯 Objective

To demonstrate SQL Injection vulnerability using DVWA (Damn Vulnerable Web Application) and understand how improper input validation can lead to unauthorized data access.

---

## 🛠 Tools Used

* DVWA (Damn Vulnerable Web Application)
* XAMPP (Apache + MySQL)
* phpMyAdmin
* Web Browser

---

## ⚙️ Setup Environment

1. Installed XAMPP and started:

   * Apache ✅
   * MySQL ✅

2. Configured DVWA:

   * Copied `config.inc.php.dist` → `config.inc.php`
   * Updated database credentials

3. Created database using DVWA setup page

---

## 🔑 Login to DVWA

Default credentials used:

* Username: `admin`
* Password: `password`

📸 Screenshot:
![Login Page](screenshots/dvwa login page.png)

---

## 🧪 SQL Injection Attack

### 🔹 Step 1: Navigate to SQL Injection Module

* DVWA → Vulnerabilities → SQL Injection

---

### 🔹 Step 2: Basic Injection Payload

```sql
' OR '1'='1
```

📸 Output:
![SQL Injection Result](screenshots/SQL Injection.png)

---

## 💥 Result

* Application returned **all user records**
* Successfully bypassed authentication
* Demonstrated data leakage vulnerability

---

## 🔍 Explanation

The original query:

```sql
SELECT * FROM users WHERE id = 'INPUT';
```

After injection:

```sql
SELECT * FROM users WHERE id = '' OR '1'='1';
```

👉 Since `1=1` is always TRUE, the database returns all records.

---

## 🚀 Advanced SQL Injection

### 🔹 Finding Number of Columns

```sql
1' ORDER BY 1 --
1' ORDER BY 2 --
1' ORDER BY 3 --
```

📸 Screenshot:
![Column Detection](screenshots/attacking number of columns.png)

---

### 🔹 UNION-Based Injection

```sql
1' UNION SELECT user, password FROM users --
```

👉 Extracts:

* Usernames
* Password hashes

---

## 🧑‍💻 Additional Observations

* Created additional users using phpMyAdmin
* Observed that SQL Injection retrieves all users from database table

📸 Screenshot:
![User Creation](screenshots/User ID Creation.png)

---

## ⚠️ Impact

* Authentication bypass
* Data exposure
* Unauthorized database access
* Risk of full system compromise

---

## 🛡 Prevention Techniques

* Use **Prepared Statements**
* Input validation & sanitization
* Parameterized queries
* Use ORM frameworks
* Least privilege database access

---

## 📌 Conclusion

This task demonstrates how SQL Injection can compromise a web application by exposing sensitive data. Proper input validation and secure coding practices are essential to prevent such vulnerabilities.

---

## 📁 Project Structure

```
Task-3-SQL-Injection/
│
├── screenshots/
│   ├── dvwa login page.png
│   ├── SQL Injection.png
│   ├── attacking number of columns.png
│   ├── User ID Creation.png
│
└── README.md
```

---

## 🎯 Learning Outcome

* Understood SQL Injection fundamentals
* Performed real-world exploitation
* Learned secure coding practices

---

## 🔗 References

* https://owasp.org/www-community/attacks/SQL_Injection
* https://portswigger.net/web-security/sql-injection
* https://en.wikipedia.org/wiki/SQL_injection

---
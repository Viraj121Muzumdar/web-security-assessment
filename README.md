# Web Application Security Assessment - OWASP Juice Shop

## **🔍 Overview**
This repository contains the vulnerability assessment of the OWASP Juice Shop application. We identified multiple security flaws using **OWASP ZAP** and **Burp Suite**, including SQL Injection, XSS, and CSRF.

---

## **📌 Tools Used**
✅ **OWASP ZAP** - Automated vulnerability scanning  
✅ **Burp Suite** - Manual web security testing  

---

## **📌 Vulnerabilities Identified**
### **1️⃣ SQL Injection**
- **Issue:** The login form allows SQL injection.  
- **Exploit Used:** `' OR '1'='1`  
- **Impact:** Allows unauthenticated login.  
- **Mitigation:** Use **prepared statements** in SQL queries.

### **2️⃣ Cross-Site Scripting (XSS)**
- **Issue:** User input fields allow JavaScript execution.  
- **Payload Used:** `<script>alert('XSS')</script>`  
- **Impact:** Attacker can inject malicious scripts.  
- **Mitigation:** Implement **input sanitization & CSP (Content Security Policy)**.

### **3️⃣ Cross-Site Request Forgery (CSRF)**
- **Issue:** Lack of CSRF token in POST requests.  
- **Exploit Used:** CSRF request to change user email.  
- **Impact:** Allows an attacker to perform actions on behalf of users.  
- **Mitigation:** Implement **CSRF tokens** in sensitive actions.

---

## **📌 Screenshots**
📌 **SQL Injection Attack Screenshot**  
📌 **XSS Exploit in Burp Suite**  
📌 **CSRF Attack Proof**  
📌 **OWASP ZAP Report Screenshot**  

---

## **📌 How to Run Your Own Security Tests**
1. **Launch OWASP Juice Shop:**  
   ```sh
   docker run -p 3000:3000 bkimminich/juice-shop

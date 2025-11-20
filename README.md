

# **Cybersecurity Internship – Week 1, Week 2 & Week 3 Tasks (Final Submission)**



If you want, I can also format an entire professional README with this heading included.

This repository contains all three weekly tasks completed during the **Cybersecurity Internship Program**, including secure API development, authentication, security testing, and final reporting.

---

# 📁 **Project Structure**

```
Cybersecurity-Internship-Tasks/
│
├── Week1_Security_Assessment/
│   ├── OWASP_Juice_Shop_Report.pdf
│   ├── zap_scan_results/
│   └── screenshots/
│
├── Week-2-Assignment/
│   ├── app.js
│   ├── userRoutes.js
│   ├── authMiddleware.js
│   ├── usercontrollers.js
│   ├── package.json
│   └── README.md
│
├── Week-3-Assignment/
│   ├── logger.js  (Winston logging)
│   ├── nmap_scan.png
│   ├── checklist.md
│   └── README.md
│
└── Final_Report.docx
```

# ✅ **Week 1 – Security Assessment**

### ✔️ Performed tasks

* Installed **OWASP Juice Shop**
* Identified common security vulnerabilities
* Performed scanning using:

  * ⚡ **OWASP ZAP**
  * 🌐 Browser-based manual testing
* Captured screenshots of vulnerabilities
* Exported **ZAP Scan Report**
* Wrote a detailed **Security Assessment Report**

### 📎 Files Included

* `OWASP_Juice_Shop_Report.pdf`
* `zap_scan_results/`
* `screenshots/`

<img width="1823" height="1039" alt="xss_error_handling png" src="https://github.com/user-attachments/assets/9f22b89b-2486-48e2-8b67-c43cb7c25f8f" />

<img width="1920" height="1200" alt="zap_full_scan png" src="https://github.com/user-attachments/assets/18b36cc0-4a68-4f13-a895-5e1f588a3baf" />

<img width="1920" height="1130" alt="zap_quickstart png" src="https://github.com/user-attachments/assets/9a065076-f5a9-440e-b761-0c384ee96d1f" />

<img width="1920" height="1130" alt="zap_scan_export_ready png" src="https://github.com/user-attachments/assets/a69942fb-b635-48c0-a8a6-cab2b0ef5f91" />


---

# ✅ **Week 2 – Secure API Development (Node.js)**

### 📌 Features Implemented

| Feature                         | Status |
| ------------------------------- | ------ |
| Input Validation (validator.js) | ✔️     |
| Input Sanitization              | ✔️     |
| Password Hashing (bcrypt)       | ✔️     |
| JWT Token Authentication        | ✔️     |
| Helmet.js for secure headers    | ✔️     |
| Login + Signup APIs             | ✔️     |
| Error handling                  | ✔️     |

---

## 🔐 **Signup API**

**POST** `/api/signup`

### Request Body:

```json
{
  "email": "example@test.com",
  "password": "123456"
}
```

### Response:


<img width="1919" height="1153" alt="thunder-client signup request" src="https://github.com/user-attachments/assets/0eae4aae-263c-4a05-ac67-50deb61182ed" />

```

---

## 🔐 **Login API**

**POST** `/api/login`

### Request Body:

```json
{
  "email": "example@test.com",
  "password": "123456"
}
```

### Response:


<img width="1919" height="1152" alt="thunder-client login request" src="https://github.com/user-attachments/assets/23094a4c-b15f-41d9-b879-de342450a05b" />


---

## 🛡️ Middleware Added

### **Helmet.js**

```js
app.use(helmet());
```

### **JWT Auth Middleware**

```js
module.exports = function(req, res, next) {
    const token = req.headers.authorization?.split(" ")[1];
    if (!token) return res.status(401).send("Access denied");

    try {
        const decoded = jwt.verify(token, "secret123");
        req.user = decoded;
        next();
    } catch (err) {
        return res.status(400).send("Invalid token");
    }
};
```

---

# ✅ **Week 3 – Advanced Security + Logging + Testing**

### ✔️ Tasks Completed

### 🧪 1. **Basic Penetration Testing (Nmap)**

Command used:

```
nmap -sV localhost
```

Output saved in:
<img width="1431" height="512" alt="nmap,ncap" src="https://github.com/user-attachments/assets/41004f86-3eff-4789-aa04-fc5637304a87" />


---

### 📝 2. **Logging with Winston**

Created `logger.js`:

```js
const winston = require('winston');

const logger = winston.createLogger({
    transports: [
        new winston.transports.Console(),
        new winston.transports.File({ filename: 'security.log' })
    ]
});

logger.info("Application started");

module.exports = logger;
```

---

### 🧾 3. **Security Best Practices Checklist**

Included items:

* Validate all inputs
* Use HTTPS
* Hash & salt passwords
* Use Helmet.js
* Disable x-powered-by
* Enable logging & monitoring
* Use JWT for authentication


# 🚀 **How to Run This Project**

### 1️⃣ Install Dependencies

```
npm install
```

### 2️⃣ Start Server

```
node app.js
```

Server runs on:

```
http://localhost:3000
```

# 🙋‍♀️ **Author**

**Maha Fatima**
Cybersecurity Internship – Final Submission




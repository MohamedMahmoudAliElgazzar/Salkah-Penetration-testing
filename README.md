# 🔐 Salkah Mobile App – Security Audit & Hardening

This repository documents the penetration testing and remediation efforts conducted on the **Salkah** mobile application, built with Flutter (frontend) and Node.js (backend). The primary objective was to identify and fix security vulnerabilities across the app’s authentication, API communication, and session handling flows.

---

## 📌 Project Overview

**Salkah** is a location-based tracking and complaints mobile app for public transport users. It collects and transmits sensitive data such as:

- Live GPS locations
- User credentials
- Complaint reports

Technologies used:
- **Frontend**: Flutter
- **Backend**: Node.js (Express)
- **Database**: MySQL hosted on Railway

---

## 🔐 Security Objectives

- Prevent unauthorized access to APIs and user data
- Encrypt data in transit (HTTPS)
- Enforce secure authentication (JWT)
- Block abuse with rate limiting and CAPTCHA
- Align findings with OWASP Mobile Top 10 risks

---

## 🧪 Methodology

- **White-box testing**: Full access to source code
- **Static code review**: Flutter + Node.js
- **Manual API fuzzing**: Using Postman, curl
- **Token/session analysis**: JWT flow verification
- **OWASP M10 mapping**: Each issue classified accordingly

---

## 🛠️ Tools Used

- Postman – API testing
- curl – Request simulation
- Burp Suite – Manual inspection
- JWT.io – Token decoding
- Railway Logs – Server request tracing
- Google reCAPTCHA – Bot defense
- express-rate-limit – Rate limiting

---

## 📉 Vulnerabilities Found

| Vulnerability                   | Severity  | OWASP Ref | OSI Layer      | Status |
|--------------------------------|-----------|-----------|----------------|--------|
| Lack of API authentication     | Critical  | M6        | App Layer (L7) | ✅ Fixed |
| Open CORS policy               | High      | M3        | App Layer (L7) | ✅ Fixed |
| JWT not implemented            | High      | M4        | App Layer (L7) | ✅ Fixed |
| No HTTPS                       | High      | M3        | Transport (L4) | ✅ Fixed |
| No rate limiting / CAPTCHA     | Medium    | M1/M4     | App Layer (L7) | ✅ Fixed |
| Weak password policy           | Medium    | M4        | App Layer (L7) | ✅ Fixed |
| No email verification          | Informational | M1     | App Layer (L7) | ✅ Fixed |

---

## ✅ Fixes Implemented

- JWT middleware added to all protected routes
- CORS policy restricted to frontend origin only
- Enforced HTTPS via Railway and Flutter networking
- Implemented password strength validation on both ends
- Google reCAPTCHA integrated on signup
- Rate limiting using express-rate-limit
- Email verification token flow with is_verified flag

---

## 📁 Structure

```
📦 salkah-security
 ┣ 📁 backend
 ┃ ┗ 📜 server.js
 ┣ 📁 frontend
 ┃ ┗ 📜 home.dart, live_tracking.dart
 ┣ 📄 README.md
 ┗ 📄 Penetration_Testing_Report.pdf
```

---

## 📄 Report

Full security report available in this repo:  
📎 [Penetration_Testing_Report.pdf](Penetration_Testing_Report__Mobile_App_(Flutter__Node.js).pdf)

---

## 🧑‍💻 Author

**Mohamed Mahmoud Elgazzar**  
Cybersecurity Enthusiast | Mobile App Security | Penetration Testing  
📧 mohamed.mahmoud.elgazzar@gmail.com  
🔗 [GitHub](https://github.com/MohamedMahmoudAliElgazzar) | [LinkedIn](https://linkedin.com/in/mohamed-mahmoud-680040235)

---

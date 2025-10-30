# 🔐 Task 5 — Web Application Penetration Testing  
*ApexPlanet Cybersecurity Virtual Internship*

---

## 🧩 Objective
The goal of this task is to perform *Web Application Vulnerability Assessment and Penetration Testing (VAPT)* in a controlled lab environment.  
It involves identifying, exploiting, and mitigating common web application vulnerabilities based on the *OWASP Top 10* framework.

---

## 🧠 Learning Outcomes
- Understand the *architecture of web applications*
- Identify and exploit *common vulnerabilities* such as SQL Injection, XSS, and Authentication Bypass
- Use *Burp Suite* and *OWASP ZAP* for web traffic interception and scanning
- Apply *manual testing techniques* to validate security flaws
- Document findings and provide *recommendations for mitigation*

---

## ⚙ Lab Setup
| Component | Role | Example Target | Description |
|------------|------|----------------|--------------|
| Kali Linux | Attacker / Tester | — | Used to perform scanning and attacks |
| DVWA / bWAPP / WebGoat | Vulnerable Web App | localhost / 127.0.0.1 | Target environment for testing |
| Tools | Burp Suite, OWASP ZAP, Browser DevTools | — | Used for web app penetration testing |

---

## 🕵 Phase 1 — Reconnaissance & Information Gathering
*Objective:* Identify the structure, technologies, and endpoints of the target web application.

*Actions Performed:*
- Checked headers and cookies via *Burp Suite*  
- Identified input fields and request parameters  
- Mapped out site directories and entry points  

*Commands / Tools Used:*
```bash
# Intercepting requests
Burp Suite → Proxy → Intercept → ON



## 💉 Phase 2 — SQL Injection Testing

Objective: Test input fields for database query vulnerabilities.

Actions:

Injected payloads into login and search forms

Observed SQL errors and responses


Sample Payloads:

' OR '1'='1
admin' --

Tools Used: Burp Suite Intruder, SQLMap (optional)

Finding:
Successful login without valid credentials confirmed SQL Injection vulnerability.


---

⚠ Phase 3 — Cross-Site Scripting (XSS)

Objective: Detect reflected and stored XSS vulnerabilities.

Payloads Tested:

<script>alert('XSS')</script>

Result:
Popup triggered on comment box submission, confirming XSS vulnerability.


---

🔑 Phase 4 — Authentication & Session Management Testing

Objective: Check for weak login mechanisms or session hijacking.

Checks Performed:

Weak password testing (admin/admin, root/root)

Session cookie manipulation

Logout and session expiration behavior


Finding:
Session did not expire after logout — indicating broken authentication issue.


---

🧰 Phase 5 — Vulnerability Scanning (Automation)

Objective: Automate web application scanning for broader coverage.

Using OWASP ZAP:

1. Open OWASP ZAP → Enter target URL (DVWA)


2. Start Active Scan


3. Review Alerts → Filter High / Medium vulnerabilities



Result:
OWASP ZAP identified issues such as X-Frame-Options missing, Cross-Domain Misconfiguration, and SQLi vectors.


---

🧮 Phase 6 — Risk Analysis

Vulnerability	Severity	Impact	Recommendation

SQL Injection	Critical	Database compromise	Use parameterized queries
Stored XSS	High	Script execution in user’s browser	Validate and sanitize input
Weak Authentication	High	Unauthorized access	Enforce strong passwords, session timeout
Missing Security Headers	Medium	Clickjacking, data exposure	Add Content-Security-Policy, X-Frame-Options
Info Disclosure	Low	Minor data leak	Hide stack traces, disable debug mode



---

🧾 Phase 7 — Reporting and Recommendations

Each finding should include:

Vulnerability Title

Impact Summary

Steps to Reproduce

Evidence (screenshots or logs)

Mitigation Recommendation


Example:

Title: SQL Injection in Login Form
Evidence: Login bypass using ' OR '1'='1
Impact: Unauthorized access to admin dashboard
Recommendation: Use prepared statements, input validation


---

📂 Deliverables

scans/zap_scan_report.html — ZAP automated scan results

burp_logs/ — Captured requests and responses

screenshots/ — 10 proof images of each test performed

notes/task5_analysis.md — Summary of findings and mitigations



---

⚠ Ethics & Legal Disclaimer

All penetration testing activities were performed only on authorized lab systems within a controlled environment.
Performing similar activities on unauthorized systems is illegal and punishable under cybersecurity laws.

## Linkedin Video Link
   https://www.linkedin.com/posts/palak-baranwal-a98145337_cybersecurity-websecurity-ethicalhacking-activity-7389706164277673984-BKdd?utm_source=social_share_send&utm_medium=android_app&rcm=ACoAAFSPZ9QBM7MH4wKOnhLjjQttu_AWlDqDMA0&utm_campaign=whatsapp

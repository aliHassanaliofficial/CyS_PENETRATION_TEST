# Penetration Testing Report

## Project Details
**Contributors:**  
- Youssef Ayman Makram (2305085)  
- Ali Hassan Ali Metwalli (2305081)  

---

## Key Findings
1. **Hidden Admin Path**
2. **Brute-force Attack Vulnerability on Admin Login**
3. **Cross-Site Scripting (XSS)**
4. **SQL Injection**

---

## Scope and Methodology
**Tools Used:**
- Burp Suite
- OWASP ZAP
- Hydra
- Dirb

---

## Detailed Vulnerabilities

### 1. Enumeration to Find Admin Path
- **Description:** Hidden admin paths were discovered by analyzing URL structures.
- **Risk:** High
- **Details:** Attempted various known admin directory patterns until successful.
- **Example:** URLs structured as `/#/nedded_directory` revealed sensitive information.

---

### 2. Brute Force on Admin Credentials
- **Description:** Admin login was vulnerable to brute-force attacks.
- **Risk:** High
- **Evidence:** Successfully retrieved the password for `admin@juice-sh.op` using brute-force tools.
- **Remediation:**
  - Enforce strong password policies.
  - Implement CAPTCHA.
  - Enable account lockout after failed login attempts.

---

### 3. XSS in Product Search
- **Description:** The search bar did not sanitize user inputs, allowing JavaScript injection.
- **Risk:** High
- **Evidence:** Successfully injected the following script:
  ```html
  <script>alert(document.cookie);</script>
  ```

---

### 4. SQL Injection
- **Description:** The email field allowed SQL injection, enabling bypass of authentication.
- **Risk:** Very High
- **Evidence:** Successfully injected:
  ```sql
  ' OR TRUE --
  ```
  - Reference: [SQL Injection Payload List](https://github.com/payloadbox/sql-injection-payload-list)

---

## Screenshots and Video Links

### Screenshots
1. Enumeration to Find Admin Path
2. Brute Force on Admin Credentials
3. XSS in Product Search

### Video Evidence
[Video Link](https://drive.google.com/drive/folders/1MhpdzsxIximRSnihcwAhqdprt6lLsTFR?usp=sharing)

---

## Notes
- Screenshots during testing and video evidence are provided for each vulnerability.

# 10.5. Common Threats and Mitigation Techniques

## Introduction

Modern systems face a wide range of security threats that can compromise data integrity, privacy, and system availability. To build a resilient and secure system, it's important to understand common security threats and the techniques that can be applied to mitigate them. In this section, we will cover some of the most common threats faced by systems and applications, including **SQL injection**, **Cross-Site Scripting (XSS)**, **Distributed Denial of Service (DDoS)**, and **Man-in-the-Middle (MITM) attacks**. We will also explore the mitigation techniques that can be used to protect your system from these threats.

## 1. SQL Injection (SQLi)

### What It Is:
**SQL injection** occurs when an attacker manipulates input fields to inject malicious SQL queries into an application’s database. This can allow attackers to view, modify, or delete data from the database, or even take control of the database server.

### Mitigation Techniques:
1. **Parameterized Queries:** Always use parameterized queries or prepared statements when interacting with databases. This ensures that input values are treated as data, not executable code.
2. **Input Validation:** Validate all user inputs to ensure they conform to expected types and formats.
3. **Least Privilege for Database Users:** Restrict the database user's permissions to limit the scope of what can be affected in the event of a successful SQL injection attack.
4. **Web Application Firewalls (WAFs):** Use WAFs to detect and block SQL injection attempts before they reach the application.

### Example:
An attacker submits an input like `1 OR 1=1` in a vulnerable login form, which modifies the underlying SQL query to always return true, granting unauthorized access to the system.

---

## 2. Cross-Site Scripting (XSS)

### What It Is:
**Cross-Site Scripting (XSS)** allows attackers to inject malicious scripts into webpages that are then executed in the user’s browser. XSS attacks can be used to steal session cookies, redirect users to malicious sites, or perform other actions in the context of the compromised user.

### Mitigation Techniques:
1. **Output Encoding:** Ensure that user-generated content is properly encoded when displayed in HTML pages, preventing it from being interpreted as executable code.
2. **Input Validation:** Sanitize all user inputs to remove or escape potentially dangerous characters (e.g., `<`, `>`, and `"`) that could be used in XSS attacks.
3. **Content Security Policy (CSP):** Implement a CSP to restrict which resources (scripts, styles, etc.) can be loaded by the browser, reducing the risk of executing malicious scripts.
4. **HTTP-Only Cookies:** Use HTTP-Only flags for session cookies to prevent them from being accessed via JavaScript, reducing the risk of session hijacking.

### Example:
An attacker embeds a malicious script in a comment field, which is then executed when another user views the comment. The script can steal the user's session token or redirect them to a phishing site.

---

## 3. Distributed Denial of Service (DDoS) Attacks

### What It Is:
**DDoS attacks** involve overwhelming a server, network, or service with a flood of traffic, rendering the system unavailable to legitimate users. Attackers typically use a network of compromised devices (a botnet) to generate this traffic.

### Mitigation Techniques:
1. **Rate Limiting and Throttling:** Limit the number of requests a user or IP address can make in a given timeframe to reduce the impact of traffic surges.
2. **Traffic Filtering:** Use traffic filtering to block traffic from suspicious or malicious IP addresses, particularly those involved in known DDoS attacks.
3. **Content Delivery Network (CDN):** Use a CDN to absorb and distribute traffic across multiple edge servers, preventing the origin server from being overwhelmed.
4. **Auto-Scaling Infrastructure:** Implement auto-scaling to dynamically increase resources in response to high traffic loads, helping maintain availability during attacks.

### Example:
An attacker orchestrates a DDoS attack against an e-commerce platform during a major sale event, causing service disruptions by overwhelming the site with traffic from thousands of compromised devices.

---

## 4. Man-in-the-Middle (MITM) Attacks

### What It Is:
In a **Man-in-the-Middle (MITM)** attack, an attacker intercepts communication between two parties (such as a client and a server) to eavesdrop, alter data, or inject malicious content without the users' knowledge.

### Mitigation Techniques:
1. **Use HTTPS (SSL/TLS):** Always encrypt communication using HTTPS to protect against eavesdropping and ensure that transmitted data remains secure.
2. **Mutual TLS (mTLS):** For sensitive internal communications between services, implement mutual TLS to ensure that both parties in the communication are authenticated.
3. **HSTS (HTTP Strict Transport Security):** Enforce HTTPS across the entire website by using HSTS, which instructs browsers to only connect via HTTPS.
4. **Certificate Pinning:** Pin public keys or certificates to prevent attackers from using fraudulent certificates to intercept traffic.

### Example:
An attacker sets up a rogue Wi-Fi hotspot in a coffee shop and intercepts traffic from users logging into their email accounts, capturing credentials in an unencrypted communication channel.

---

## 5. Cross-Site Request Forgery (CSRF)

### What It Is:
**CSRF** exploits the trust that a web application has in a user's browser. By tricking the user into making an unintended request (e.g., clicking on a malicious link), an attacker can perform actions on behalf of the user, such as transferring funds or changing account details.

### Mitigation Techniques:
1. **CSRF Tokens:** Use anti-CSRF tokens to ensure that requests are legitimate and originate from the user. These tokens are unique per session and prevent unauthorized commands from being executed.
2. **SameSite Cookies:** Set the `SameSite` attribute on cookies to prevent them from being sent with cross-site requests, reducing the risk of CSRF attacks.
3. **Verify Referrers:** Check the `Referrer` header to ensure that incoming requests are coming from trusted sources.

### Example:
An attacker sends an email with a link that, when clicked, executes a request to transfer money from the victim’s account. The web application processes the request because it appears to come from the legitimate user session.

---

## 6. Insecure Direct Object References (IDOR)

### What It Is:
**Insecure Direct Object References (IDOR)** occur when an application exposes internal objects, such as database records or files, in a way that allows attackers to manipulate or access unauthorized resources by modifying input parameters.

### Mitigation Techniques:
1. **Access Control Checks:** Ensure that access control checks are performed for every request to verify whether the user has permission to access the resource.
2. **Use Indirect Object References:** Avoid exposing internal object references (e.g., database IDs) directly. Instead, use indirect references such as UUIDs or hashed identifiers.
3. **Input Validation and Output Encoding:** Implement input validation and output encoding to prevent attackers from tampering with object references.

### Example:
A user accesses their account by modifying a URL parameter (e.g., `user_id=123`). By changing the `user_id` to another number (e.g., `user_id=456`), the attacker can access another user’s account.

---

## Conclusion

Understanding and mitigating common security threats is key to protecting modern systems from attacks. SQL injection, XSS, DDoS, MITM, CSRF, and IDOR are among the most prevalent threats, but each can be effectively mitigated with proper security measures. By implementing best practices such as encryption, secure coding, rate limiting, and strong access controls, organizations can defend against these threats and ensure the security of their systems.

---

[Next: Module 11 Introduction](./module_11/module_11_intro.md)

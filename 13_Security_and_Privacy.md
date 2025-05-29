# 13. Security & Privacy in System Design

---

## Why Security & Privacy Matter

Security and privacy are essential for protecting user data, maintaining trust, and complying with legal requirements. Security must be considered at every stage of system design.

---

## Security Principles

- **Least Privilege:** Grant only necessary permissions.
- **Defense in Depth:** Multiple layers of security controls.
- **Fail Securely:** Systems should default to a secure state on failure.
- **Secure by Design:** Security is foundational, not an afterthought.

---

## Common Threats

- **SQL Injection**
- **Cross-Site Scripting (XSS)**
- **Cross-Site Request Forgery (CSRF)**
- **Broken Authentication and Session Management**
- **Sensitive Data Exposure**
- **Denial of Service (DoS/DDoS)**
- **Insider Threats**

---

## Authentication & Authorization

- Use strong authentication (multi-factor, OAuth2).
- Implement role-based access control (RBAC).
- Timeout and rotate sessions/tokens.
- Validate all tokens and credentials.

---

## Data Protection

- Encrypt data at rest and in transit (TLS, AES).
- Hash passwords with salt (bcrypt, Argon2).
- Mask or redact sensitive fields in logs.
- Use secrets management tools (Vault, AWS KMS).

---

## Secure APIs

- Validate and sanitize all input.
- Use HTTPS for all endpoints.
- Rate limit and monitor APIs.
- Use secure headers (CORS, CSP, HSTS).

---

## Secure Storage

- Avoid storing sensitive data unless necessary.
- Apply data minimization and retention policies.
- Use secure key management.

---

## Privacy by Design

- Collect only required data.
- Provide users with control over their data (GDPR, CCPA).
- Anonymize or pseudonymize personal information.

---

## Monitoring & Incident Response

- Enable audit logs for sensitive actions.
- Set up intrusion detection and anomaly alerts.
- Have a clear incident response plan.

---

## Compliance

- GDPR, HIPAA, PCI-DSS, SOC2 as applicable.
- Document data flows, policies, and consent mechanisms.

---

## Security Testing

- Automated static and dynamic analysis (SAST, DAST).
- Regular penetration testing (internal and third-party).
- Dependency scanning for vulnerabilities (e.g., Snyk).

---

## Secure Deployment

- Patch vulnerabilities promptly.
- Limit access to production systems.
- Automate security checks in CI/CD pipelines.

---

## Interview Questions

- How do you prevent SQL injection?
- What is the difference between authentication and authorization?
- How would you secure an API?
- How do you handle secrets in your application?

---

## Exercises

- Implement password hashing and validation.
- Set up TLS for a web service.
- Perform a basic security audit on a sample app.
- Write a privacy policy for a new product.

---

## References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Mozilla Security Guidelines](https://infosec.mozilla.org/guidelines/web_security.html)
- [GDPR Overview](https://gdpr.eu/)

---

## Summary

Security and privacy are non-negotiable in system design. Consider them at every stage and keep up to date with evolving threats and best practices.

---

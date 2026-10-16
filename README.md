# Web Application Penetration Testing Portfolio

A collection of **authorized web application security assessments** conducted in controlled laboratory environments. This repository documents testing methodology, verified findings, supporting evidence, and remediation recommendations.

> **Ethical testing:** All published assessments use intentionally vulnerable applications or environments where testing is explicitly authorized. Findings are educational lab results and must not be interpreted as vulnerabilities in unrelated production systems.

## Assessments

| Application | Assessment type | Findings | Report |
| --- | --- | --- | --- |
| [OWASP Juice Shop](assessments/owasp-juice-shop/README.md) | Grey-box web application security assessment (local lab) | 5 (1 Critical, 3 High, 1 Medium) | [PDF](assessments/owasp-juice-shop/report/OWASP_Juice_Shop_Pentest_Report.pdf) |

## Approach

1. **Scope and authorization** — define the permitted target and test environment.
2. **Reconnaissance** — identify accessible pages, routes, and API endpoints.
3. **Manual security testing** — assess authentication, authorization, injection, client-side behavior, and configuration.
4. **Evidence and risk assessment** — document reproducible, non-destructive proof of concept, severity, and impact.
5. **Remediation reporting** — map findings to OWASP categories and recommend mitigations.

## Tools and Frameworks

- **Tools:** Burp Suite Community Edition (Proxy and Repeater), Kali Linux, Docker, Chromium, browser developer tools.
- **References:** OWASP Web Security Testing Guide (WSTG), OWASP Top 10 (2021), CVSS v3.1.

## Repository Structure

```text
web-application-penetration-testing/
├── README.md
└── assessments/
    └── owasp-juice-shop/
        ├── README.md
        └── report/
            └── OWASP_Juice_Shop_Pentest_Report.pdf
```

Additional assessments may be added as new, authorized testing is completed. This repository is separate from CTF and guided lab write-ups.

## Responsible Disclosure and Privacy

Do not commit session tokens, passwords, private customer data, sensitive proxy captures, or unredacted identifiers. Published screenshots and sample requests should be reviewed and sanitized before upload.

## Author

**Selvi Melani**  
Cybersecurity / Web Application Security Portfolio

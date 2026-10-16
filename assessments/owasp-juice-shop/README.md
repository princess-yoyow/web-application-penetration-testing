# OWASP Juice Shop — Grey-Box Penetration Test

**Assessment date:** 14 October 2026  
**Environment:** Self-hosted OWASP Juice Shop instance (`localhost:3000`) running in Docker on a Kali Linux virtual machine  
**Assessment:** Authorized, non-destructive laboratory evaluation  
**Report:** [View the full 20-page penetration test report](report/OWASP_Juice_Shop_Pentest_Report.pdf)

## Overview

This project documents a grey-box web application security assessment of OWASP Juice Shop, an intentionally vulnerable training application. The assessment covered the storefront, REST API, and administrative interface. Testing combined reconnaissance with manual verification through Burp Suite Proxy and Repeater, with findings mapped to the OWASP Top 10 (2021) and assessed using CVSS v3.1.

All observations are limited to this controlled local lab instance. They do not represent findings against a third-party or production service.

## Findings at a Glance

| ID | Finding | Severity | CVSS v3.1 | OWASP Top 10 (2021) |
| --- | --- | --- | --- | --- |
| F-01 | SQL injection in login / authentication bypass | Critical | 9.8 | A03: Injection |
| F-02 | Administrative panel access control weakness | High | 8.6 | A01: Broken Access Control |
| F-03 | Insecure Direct Object Reference on shopping basket | High | 7.1 | A01: Broken Access Control |
| F-04 | Sensitive file directory exposure via `robots.txt` | High | 7.5 | A05: Security Misconfiguration |
| F-05 | DOM-based Cross-Site Scripting in search | Medium | 6.1 | A03: Injection |

**Total:** 5 findings — 1 Critical, 3 High, 1 Medium. Severity ratings reflect the project report's assessment of this lab application.

## Scope and Tools

- **Target:** OWASP Juice Shop storefront, REST API, and administrative interface.
- **Environment:** Kali Linux virtual machine, Docker, Chromium.
- **Testing:** Burp Suite Community Edition (Proxy and Repeater), browser developer tools, manual endpoint and access-control inspection.
- **Methodology:** OWASP WSTG-based workflow: reconnaissance, manual testing, safe proof of concept, reporting.

## Key Observations and Remediation

### Authentication and authorization

The lab demonstrated an SQL injection authentication bypass and insufficient access-control enforcement on administrative and basket endpoints. Recommended controls include parameterized queries, server-side role checks, and object-level authorization on every request.

### File exposure

A route referenced by `robots.txt` led to a browsable directory containing sensitive lab files. Recommended controls include disabling directory listings and removing sensitive files from the public web root.

### Client-side injection

The product search behavior allowed DOM-based XSS in the tested lab. Recommended controls include context-aware output handling and an appropriately configured Content Security Policy.

## Evidence and Full Report

The [technical report](report/OWASP_Juice_Shop_Pentest_Report.pdf) includes evidence screenshots, relevant endpoints, impact, remediation, and lab setup details for all five findings. Review screenshots and captured HTTP data before sharing any separate artifacts.

## Limitations

- Testing covered one self-hosted, intentionally vulnerable application instance.
- Results do not establish the security posture of other installations or production applications.
- Findings were verified in a lab; this project does not claim post-remediation retesting or an enterprise-scale assessment.

## Ethical Use

This report is a portfolio sample of authorized security testing. Do not attempt equivalent techniques against applications without explicit permission.

[← Back to WAPT portfolio](../../README.md)

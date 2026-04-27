# DevSecOps Security Pipeline

A GitHub Actions-based CI/CD security pipeline that automates vulnerability 
scanning, secrets detection, and static code analysis on every push and pull 
request — enforcing secure SDLC practices before code reaches production.

## Overview

This project demonstrates end-to-end DevSecOps pipeline implementation using 
industry-standard open-source security tools integrated directly into the 
development workflow.

## Security Controls Implemented

| Control | Tool | Purpose |
|---|---|---|
| Secrets Detection | Gitleaks | Prevents hardcoded credentials from being committed |
| Vulnerability Scanning | Trivy | Scans filesystem for HIGH/CRITICAL CVEs |
| Static Code Analysis (SAST) | Bandit | Identifies insecure Python code patterns |

## How It Works

1. Developer pushes code or opens a pull request
2. GitHub Actions triggers three parallel security jobs automatically
3. **Gitleaks** scans for exposed secrets and API keys
4. **Trivy** scans the codebase for known vulnerabilities (CVEs)
5. **Bandit** performs SAST analysis on Python source code
6. Pipeline **blocks the merge** if HIGH or CRITICAL findings are detected
7. Developer remediates findings and re-triggers the pipeline

## Frameworks & Standards Aligned

- OWASP Top 10 (A02: Cryptographic Failures, A06: Vulnerable Components)
- NIST SP 800-53 (SI-10, SA-11, RA-5)
- Secure SDLC best practices

## Tools & Technologies

- **CI/CD:** GitHub Actions
- **Secrets Scanning:** Gitleaks
- **Vulnerability Scanning:** Trivy (Aqua Security)
- **SAST:** Bandit (Python)
- **Language:** Python
- **Platform:** GitHub

## Pipeline Triggers

- Push to `main` branch
- Pull requests targeting `main` branch

## Sample Pipeline Output

[Trivy] Scanning filesystem for vulnerabilities...
CRITICAL: CVE-2023-XXXX found in requests==2.27.0
ACTION: Merge blocked — remediate before proceeding.
[Gitleaks] Scanning for secrets...
No secrets detected. ✅
[Bandit] Running SAST on Python files...
No high severity issues found. ✅

## Skills Demonstrated

- GitHub Actions CI/CD pipeline design
- Security tool integration (SAST, SCA, secrets scanning)
- Automated vulnerability management
- Secure SDLC enforcement
- DevSecOps pipeline architecture

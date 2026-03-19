# Security Policy

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| latest  | :white_check_mark: |

## Reporting a Vulnerability

If you discover a security vulnerability, please report it responsibly:

1. **Do not** open a public issue
2. Email: admin@tfs-tin.org
3. Include a description of the vulnerability, steps to reproduce, and potential impact
4. You will receive a response within 48 hours

## Security Measures

This repository employs the following security controls:

- **Code Scanning:** CodeQL analysis runs on every push and PR, plus weekly scheduled scans
- **Dependency Management:** Dependabot monitors and auto-updates vulnerable dependencies
- **Dependency Review:** PRs are blocked if they introduce high-severity dependency vulnerabilities
- **Secret Protection:** Secret scanning and push protection are enabled to prevent credential leaks
- **Copilot Autofix:** AI-assisted vulnerability remediation for code scanning alerts

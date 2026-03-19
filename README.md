# Security Protocols

GitHub code security configuration for SOC 2 compliance.

## Enabled Security Features

| Feature | Status | Configuration |
|---------|--------|---------------|
| Code Scanning (CodeQL) | Automated | `.github/workflows/codeql.yml` |
| Copilot Autofix | Auto-enabled | No config needed |
| Dependabot Alerts & Updates | Automated | `.github/dependabot.yml` |
| Dependency Review | PR enforcement | `.github/workflows/dependency-review.yml` |
| Secret Scanning | Enable in Settings | UI toggle |
| Push Protection | Enable in Settings | UI toggle |
| Security Overview | Org-level | No config needed |

## Post-Push Setup (GitHub UI)

After pushing this repo, enable these in **Settings > Code security and analysis**:

1. **Secret scanning** — toggle ON
2. **Push protection** — toggle ON
3. **Dependabot alerts** — toggle ON
4. **Dependabot security updates** — toggle ON

## Custom Dependabot Auto-Triage Rules

Create these in **Settings > Code security > Dependabot > New rule**:

- **Auto-dismiss low-severity dev deps:** Severity=low, Scope=development, Action=Dismiss
- **Auto-PR for critical runtime deps:** Severity=critical+high, Scope=runtime, Action=Open PR

## SOC 2 Control Mapping

| SOC 2 Control | GitHub Feature |
|---------------|---------------|
| CC6.1 — Secrets management | Secret scanning + push protection |
| CC7.1 — Vulnerability management | Code scanning + Dependabot |
| CC8.1 — Change management | Dependency review + PR enforcement |
| CC7.2 — Monitoring | Security overview dashboard |
| CC7.3 — Risk assessment | Dependabot auto-triage rules |

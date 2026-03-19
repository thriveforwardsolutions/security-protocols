# Incident Response Plan

## Purpose
This plan establishes procedures for responding to security incidents detected by GitHub's security tools.

## Severity Levels

| Level | Description | Response Time | Examples |
|-------|-------------|---------------|----------|
| Critical | Active exploitation or data breach risk | Within 4 hours | Leaked production secrets, critical RCE vulnerability |
| High | Significant vulnerability with known exploit | Within 24 hours | High-severity CVE in runtime dependency |
| Medium | Vulnerability with limited exploit potential | Within 1 week | Medium-severity code scanning alert |
| Low | Minor issue, no immediate risk | Within 1 month | Low-severity dev dependency alert |

## Response Procedures

### 1. Secret Leak Detected (Push Protection Bypass or Secret Scanning Alert)
1. Immediately rotate the compromised credential
2. Review access logs for unauthorized usage
3. Update the secret in all systems
4. Investigate how the secret entered the codebase
5. Document the incident and resolution

### 2. Critical/High Vulnerability (Code Scanning or Dependabot)
1. Assess if the vulnerability is exploitable in your context
2. Apply Copilot Autofix suggestion if available
3. If no autofix, manually patch or update the dependency
4. Create a PR with the fix
5. Verify the fix resolves the alert

### 3. Dependency Vulnerability (Dependabot Alert)
1. Review the Dependabot PR if auto-created
2. Test the updated dependency locally
3. Merge the PR if tests pass
4. If update causes breaking changes, document and plan migration

## Contacts

| Role | Name | Email |
|------|------|-------|
| Security Owner | Eric Campos | admin@tfs-tin.org |

## Review Schedule
This plan is reviewed quarterly and after every major incident.

- Last reviewed: 2026-03-19
- Next review: 2026-06-19

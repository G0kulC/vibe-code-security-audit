# vibe-code-security-audit

An open-source agent skill that security-checks any web app or website after vibe coding. It audits first, reports findings by severity, fixes only what you approve, then retests.

## How it works
1. **Scope**: detects your stack and marks checks that do not apply.
2. **Audit (read-only)**: reviews code and configuration.
3. **Report**: saves `security-audit/REPORT.md`, then stops.
4. **Fix**: makes small changes for the findings you approve.
5. **Retest**: updates the status of each finding.

## What it checks
| Area | Examples |
|---|---|
| Vibe-coding risks | hardcoded keys, auth bypass, open database rules, made-up packages |
| AI agents and features | prompt injection, excessive permissions, exposed model keys |
| Frontend | XSS, token storage, CSP, source maps |
| Login and SSO | sessions, MFA, OAuth/OIDC validation |
| Authorization | IDOR/BOLA, privilege escalation, tenant isolation |
| API and backend | injection, SSRF, file upload, rate limits |
| Supply chain | known CVEs, typosquatting, CI actions, base images |
| Infrastructure | TLS, CORS, secrets, logging, backups |

## Install (Claude Code)
```bash
git clone https://github.com/G0kulC/vibe-code-security-audit ~/.claude/skills/vibe-code-security-audit
```
Update later:
```bash
git -C ~/.claude/skills/vibe-code-security-audit pull
```
For other coding agents, give them `SKILL.md` as instructions.

## Use
Open your project, then ask:

- `Use vibe-code-security-audit on this project. Audit only and give me the report.`
- `Fix all Critical and High findings.`
- `Retest the fixed findings.`

## Standards
- OWASP Top 10:2025
- [OWASP ASVS 5.0.0](https://github.com/OWASP/ASVS)
- [OWASP API Security Top 10 2023](https://owasp.org/www-project-api-security/)
- [OWASP Top 10 for LLM Applications 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/)
- [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)

The last review date is at the top of `SKILL.md`.

## Updates
A weekly check (Mondays) looks for new standards and attack types. Changes are proposed as pull requests and reviewed before merging. See `CHANGELOG.md`.

## Safety and limits
- Audit only systems you own or are authorized to test.
- Never commit audit reports or secrets to a public repository.
- This does not prove an app is secure and does not replace an independent penetration test.

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md).

## License
[MIT](LICENSE)

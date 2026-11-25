# vibe-code-security-audit

An open-source agent skill that security-checks any web app or website after vibe coding: read-only audit, severity report, approved fixes, then retest.

## Use it
1. Copy `SKILL.md` into a skill folder named `vibe-code-security-audit` (for Claude Code: `~/.claude/skills/vibe-code-security-audit/SKILL.md`), or paste it as instructions into another coding agent.
2. Open your project.
3. Ask: `Use vibe-code-security-audit on this project. Audit only and give me the report.`
4. Review the report, then approve fixes: `Fix all Critical and High findings.`

## Standards
The baseline and its last review date are listed at the top of `SKILL.md`.

## Limits
This helps find and fix common problems. It does not prove an app is secure and does not replace an independent penetration test. Only audit systems you own or are authorized to test. Never commit audit reports or secrets to a public repository.

## Contributing
See `CONTRIBUTING.md`.

## License
MIT

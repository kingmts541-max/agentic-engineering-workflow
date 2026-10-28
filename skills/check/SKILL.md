---
name: check
description: Verify actual behavior against acceptance criteria or run static checks.
---

# Check

Choose the mode explicitly: `verify` or `review`.

## Verify

- Read the approved spec and its numbered acceptance criteria, if one exists.
- Run the application/system where feasible and exercise the relevant behavior; static checks alone do not prove runtime behavior.
- Run relevant format, lint, type, build, and static checks.
- Record each criterion as pass, fail, blocked, or not verified, with evidence.
- Report exact commands and outcomes. Never claim an unrun check passed.

## Review

Prefer the dedicated `review` skill. Review is a separate, read-only pass over the diff; ideally use a different model/agent than the implementer. Report findings with severity and file/line references. Do not modify code during review.

Keep verification results distinct from independent review findings.
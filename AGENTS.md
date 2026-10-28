# Agent Policy

Inspect repository instructions, git status, relevant code, and tests before editing. Preserve existing user changes. Keep scope minimal and follow project conventions.

Ask before consequential architecture/product decisions, destructive operations, risky migrations, security-policy changes, or production actions. Do not commit, push, deploy, publish, or create a PR without explicit authorization.

Never expose secrets or use production credentials/customer data in tests. Do not weaken authorization, validation, or tests to make checks pass. Add tests for meaningful behavior changes.

Run relevant checks and report exact commands and outcomes. Distinguish tests run from tests not run or blocked. Review the diff for correctness, security, compatibility, and scope creep. Report limitations honestly.
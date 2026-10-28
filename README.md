# Agentic Engineering Workflow

A tool-agnostic, approval-gated workflow for using coding agents on real software projects.

The goal is to make agents useful without letting them silently expand scope, invent product decisions, weaken security, or claim work is verified when it is not.

## Workflow

**Audit → Scope → Architect (when needed) → Approve → Develop → Verify → Test → Review → Document → Sync**

Debugging can be invoked at any stage. Not every task needs every phase: a typo may need only scope, change, and verification; a risky architectural change should use the full sequence.

## Principles

- **One source of truth:** project-specific instructions and docs in the target repository override generic examples here.
- **Inspect before changing:** audit unfamiliar or existing code before proposing modifications.
- **Approval gates:** ask before material scope changes, consequential architecture decisions, destructive operations, migrations, or security-sensitive trade-offs.
- **Verify claims:** report commands run, results, and limitations. Never claim tests passed if they were not run.
- **Minimal changes:** solve the requested problem without unrelated refactors.
- **No implicit publishing:** do not commit, push, deploy, or open external resources unless explicitly authorized.
- **Security first:** never expose secrets, weaken controls to make tests pass, or use real customer/payment data in unsafe environments.
- **Durable handoffs:** record decisions, remaining risks, and next steps in repository docs or the final response.

## Repository layout

- `AGENTS.md` — general agent policy for repositories that adopt this workflow.
- `CLAUDE.md` — Claude Code entry point importing the shared policy.
- `AGENTIC_WORKFLOW.md` — full lifecycle and approval rules.
- `agents/` — focused role prompts.
- `skills/` — reusable phase instructions.
- `adapters/` — tool-specific setup notes and command mappings.
- `templates/` — reusable planning and review artifacts.

## Quick start

1. Read `AGENTIC_WORKFLOW.md` and the relevant skill.
2. In a new or unfamiliar repository, run the **audit** phase first.
3. Define a small, testable scope before editing.
4. Agree on consequential design decisions before implementation.
5. Verify the change with relevant checks and tests.
6. Review the diff for correctness, security, regressions, and scope.
7. Document what changed and what remains unverified.

## Adopting this workflow

Copy or adapt the policy and relevant skills into your project. Preserve existing project-specific instructions; merge carefully rather than replacing them. Tool adapters are guidance, not a promise that every tool version supports identical behavior.

## License

MIT. See [LICENSE](LICENSE).

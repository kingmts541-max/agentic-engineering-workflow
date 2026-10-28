# Agentic Engineering Workflow

A tool-agnostic, approval-gated workflow for coding agents. It combines flexible phase selection with durable project state, explicit architectural decisions, acceptance criteria, and honest verification.

The goal is to make agents useful without letting them silently expand scope, invent product decisions, or claim work is verified when it is not.

## Core phases

**Scope → Audit (brownfield) → Architect → Develop → Check/Verify → Test → Review → Document → Sync**

This is a map, not a mandatory checklist. Audit first when entering an existing codebase; for greenfield work, scope first, make load-bearing decisions, scaffold, and then audit the real project. `debug` can be used at any point. Skip phases that do not add value for a particular change.

## What makes the workflow useful

- **Persistent state:** scope, specs, and reviews live in repository files, not only in chat.
- **Specs as contracts:** non-trivial designs record numbered acceptance criteria and decision status.
- **No invented decisions:** implementation pauses when a missing decision materially affects behavior, security, data, or compatibility.
- **Separate verification and review:** verify checks actual behavior against acceptance criteria; review independently inspects the diff and does not edit code.
- **Flexible depth:** Prototype, Alpha, Beta, and GA suggest increasing levels of verification, testing, review, and documentation without making every task follow every phase.
- **Sync:** reconcile scope, spec statuses, context instructions, and code after work.
- **Approval gates:** no consequential actions or publishing without permission.

## Suggested repository layout

- `AGENTS.md` — shared agent policy.
- `CLAUDE.md` — Claude Code entry point.
- `AGENTIC_WORKFLOW.md` — lifecycle, artifact ownership, and approval rules.
- `skills/` — focused instructions for each phase.
- `adapters/` — tool-specific setup notes and mappings.
- `templates/` — reusable scope, spec, and review templates.
- `docs/scope/` — living scope and progress for an adopting project.
- `docs/specs/` — proposed and approved implementation specs.
- `docs/reviews/` — independent review findings.

Adopting projects should create these state directories only when useful and should preserve their own conventions rather than blindly replacing existing instructions.

## Quick start

1. Read `AGENTIC_WORKFLOW.md` and existing project instructions.
2. For a brownfield project, audit the repository before scoping the next slice.
3. Write a bounded scope with acceptance criteria, non-goals, risks, and an appropriate workflow depth.
4. For non-trivial work, create a spec with numbered acceptance criteria and mark consequential decisions as proposed until approved.
5. Implement only the agreed scope. Pause rather than inventing a consequential decision.
6. Verify actual behavior, run appropriate tests, and independently review according to risk.
7. Sync scope/spec/context status with the real code and provide an honest handoff.

## Workflow depth

- **Prototype:** focused implementation plus self-check.
- **Alpha:** runtime verification against acceptance criteria.
- **Beta:** automated tests for changed behavior and relevant edge cases.
- **GA:** independent review and documentation/handoff in addition to the above.

These are defaults, not rigid release stages. The user decides whether the work is done.

## Tool compatibility

The workflow is tool-agnostic, but agent tools differ in their command syntax, subagent support, permissions, and context-file behavior. Treat adapter docs as guidance and verify them against the installed tool version; do not assume commands are portable verbatim.

## License

MIT. See [LICENSE](LICENSE).

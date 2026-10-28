# Agentic Engineering Workflow

A flexible, repository-first workflow inspired by proven agentic engineering practices. Use only the phases a change needs; do not force a ceremony-heavy sequence onto trivial work. The universal rule is that consequential decisions must be explicit, and implementation must not silently invent unresolved product or architecture choices.

## Core phases

The nine core skills are `scope`, `audit`, `architect`, `develop`, `check`, `test`, `review`, `document`, `sync`; `debug` can be invoked at any point. `orchestrate`, if present, is an optional convenience layer, not a required phase.

- **Scope** defines the problem, boundaries, acceptance criteria, non-goals, and appropriate workflow depth. It says what outcome is needed, not how to implement it. Keep the scope as a living status document.
- **Audit** inspects the actual repository, instructions, scripts, dependencies, architecture, security boundaries, and tests. For an existing/brownfield project, audit before scoping the next slice. Update project-specific instructions only when evidence supports the change.
- **Architect** is for non-trivial or load-bearing decisions. Record a proposed design as a durable spec in `docs/specs/`, with numbered acceptance criteria and decision status. Separate decisions the agent can make, questions that require the user, and expert recommendations.
- **Develop** implements only the agreed scope/spec. If a missing decision would change product behavior, data semantics, security, compatibility, or architecture, stop and ask. If the user explicitly authorizes an assumption, record it as **Assumed** in the spec and flag it for ratification.
- **Check — verify** runs the application or relevant system and checks the numbered acceptance criteria against actual behavior. Static checks alone are not equivalent to runtime verification.
- **Test** adds or runs an appropriate automated test suite for the changed behavior, including important edge/error paths. Do not confuse a test plan with tests that were actually run.
- **Check — review** (or the separate **Review** skill) independently inspects the diff for correctness, security, regressions, and scope creep. Prefer a different model/agent than the implementer when available. Review reports findings; it does not edit code.
- **Document** derives concise docs, release notes, or change summaries from the actual diff and decisions.
- **Sync** reconciles scope, spec status, context instructions, and actual repository state. Make surgical updates; do not rewrite unrelated documentation.

## Choosing a path

### Greenfield
Scope the outcome first, architect the stack and load-bearing decisions, scaffold the project, then audit the real scaffold before feature work.

### Brownfield
Audit first, then scope the next bounded slice. Use the architect/spec loop when the change has meaningful design choices.

### Suggested workflow depth
- **Prototype:** implement a small slice and self-check it.
- **Alpha:** add runtime verification against acceptance criteria.
- **Beta:** add/maintain automated tests for the changed behavior.
- **GA:** add an independent review and a clear documentation/handoff pass.

These are defaults, not mandatory tracks. Risk, uncertainty, and user intent determine the depth. A small typo may need only scope/change/check; a security-sensitive payment or identity change should normally receive the full path. The user decides when the work is done.

## Persistent state and artifact ownership

Use these locations when relevant; adapt to existing repository conventions instead of duplicating sources of truth.

- `docs/scope/`: living scope, slices, progress, and workflow depth.
- `docs/specs/`: proposed/approved/implemented specs and numbered acceptance criteria.
- `docs/reviews/`: independent review findings, including severity and file/line references.
- `AGENTS.md` and tool-specific entry points such as `CLAUDE.md`: durable project context and agent policy.
- `design.md`: design-system guidance, if the project has a UI/design system.
- Source and test directories: implementation and executable tests remain in the project's normal locations.
- PR body, changelog, release docs, or postmortems: user-facing change records where applicable.

Prefer status labels such as **Proposed**, **Approved**, **Implemented**, **Verified**, **Superseded**, and **Assumed**. Update statuses during Sync so the docs match reality.

## Approval gates

Ask before material scope expansion, consequential product/architecture decisions, destructive operations, meaningful dependency/licensing changes, risky data migrations, security-control changes, production actions, or publishing externally.

## Principles

- Repository-specific instructions and conventions take precedence over generic examples here.
- Separate confirmed facts from assumptions and recommendations.
- Preserve unrelated user changes; inspect repository status before editing.
- Never hard-code or expose secrets; never use production credentials or real customer data in tests.
- Never weaken security checks or tests merely to get a green result.
- No commit, push, deployment, release, or PR unless explicitly authorized.
- Report exact checks run, outcomes, blocked checks, limitations, and unresolved risks.

## Definition of done

Acceptance criteria are met or unmet items are explicit; decisions and assumptions are recorded; relevant verification and tests are reported honestly; independent review findings are resolved or acknowledged when warranted; docs reflect the actual repository state; remaining risks and next steps are clear.

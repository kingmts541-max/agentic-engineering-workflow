---
name: architect
description: Record load-bearing design decisions and acceptance criteria before implementation.
---

# Architect

Use for non-trivial changes or whenever architecture, data semantics, security, compatibility, or product behavior is load-bearing.

1. Inspect current code and conventions before proposing a design.
2. Compare viable options briefly and recommend the smallest safe design.
3. Create or update a spec in `docs/specs/` using `templates/spec.md`.
4. Include numbered acceptance criteria, boundaries, data flow, failure modes, security, compatibility, migration/rollout/rollback, and verification approach.
5. Mark the spec **Proposed** until consequential decisions are approved. Separate agent-decide items, questions for the user, and expert recommendations.
6. Do not treat an unapproved recommendation as a decision. If the user explicitly authorizes proceeding with an assumption, label it **Assumed**, state the impact, and flag it for ratification during Sync.

Scope says what outcome is needed; the spec explains how the approved design will meet it. Avoid writing an elaborate spec for trivial changes.
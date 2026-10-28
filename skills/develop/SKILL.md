---
name: develop
description: Implement the agreed scope and approved spec without inventing consequential decisions.
---

# Develop

Implement the approved scope and, when present, the approved spec. Follow local conventions, keep the diff focused, and add tests for meaningful behavior changes.

- Treat numbered acceptance criteria as the implementation contract.
- Do not silently fill in unresolved choices that affect product behavior, security, data semantics, architecture, or compatibility. Stop and ask, or use an explicitly authorized assumption recorded as **Assumed** in the spec.
- Avoid unapproved dependencies, unrelated refactors, destructive actions, and publishing.
- If implementation reveals that the spec is incomplete or wrong, stop at the decision boundary and propose a spec update before proceeding.
- Do not edit independent review reports to make findings disappear; resolve findings in code or explain why a finding is not applicable.
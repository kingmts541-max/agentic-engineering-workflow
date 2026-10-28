---
name: review
description: Independently inspect a change for defects without editing code.
---

# Review

Review the implementation diff against the approved scope/spec and local project conventions. When available, use a different model or agent from the implementer.

- Do not edit files or fix findings during the review.
- Prioritize actionable correctness defects, security/privacy issues, regressions, data-loss risks, and unmet acceptance criteria.
- Ignore unsupported speculation and style preferences that do not affect maintainability or project conventions.
- For each finding, include severity, file/line reference, impact, and a concise rationale.
- Record results in `docs/reviews/` for substantial work using `templates/review.md`; for trivial work, a concise handoff may be enough.
- If there are no findings, state the areas reviewed and any limitations. Absence of findings is not proof that the code is defect-free.
- Return control to the implementation phase for fixes; never change the code in this phase.
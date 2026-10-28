---
name: sync
description: Reconcile persistent workflow artifacts with the actual code and hand off without implicit publishing.
---

# Sync

Before handoff, inspect repository status and the actual diff. Preserve unrelated user changes.

- Reconcile the living scope's completed, incomplete, blocked, and next-slice status.
- Update spec status only to match reality: Proposed, Approved, Implemented, Verified, or Superseded. Do not mark a spec Verified without evidence.
- Ratify or keep explicit Assumed decisions visible; do not silently convert assumptions into approved decisions.
- Update `AGENTS.md`/tool-specific context only when it has become inaccurate or important durable knowledge is missing.
- Ensure docs, tests, and reported verification agree with the actual change. Keep updates surgical and avoid duplicate sources of truth.
- State completed work, checks actually run, blocked/unverified items, unresolved risks, and the next step.
- Do not commit, push, deploy, publish, or create a PR unless explicitly authorized.
---
name: audit
description: Inspect an existing codebase and establish accurate project context before changes.
---

# Audit

For an existing/brownfield repository, audit before scoping the next slice.

1. Read root and nested instructions; inspect git status and preserve unrelated user changes.
2. Map relevant directories, entry points, dependencies, scripts, data stores, integrations, and deployment/configuration surfaces.
3. Trace the requested behavior through implementation and tests. Identify invariants, trust/security boundaries, failure paths, and coverage gaps.
4. Report confirmed facts separately from assumptions and recommendations.
5. If project instructions are missing or materially inaccurate, propose evidence-based updates to `AGENTS.md` and nested `AGENTS.md` files for separate workspaces where appropriate. Do not overwrite useful project-specific instructions blindly.
6. Do not edit application code during audit unless asked.

For greenfield work, scope and decide the initial architecture first; audit the actual scaffold once it exists.
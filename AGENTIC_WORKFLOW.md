# Agentic Engineering Workflow

## Lifecycle
1. **Audit** the existing system and instructions.
2. **Scope** the problem, acceptance criteria, constraints, and non-goals.
3. **Architect** non-trivial changes; compare options and document trade-offs.
4. **Approve** consequential decisions before implementation.
5. **Develop** the smallest coherent change.
6. **Verify** with relevant static checks/builds/manual checks.
7. **Test** behavior and important failure paths.
8. **Review** the diff independently for defects, security, regressions, and scope creep.
9. **Document** durable decisions and relevant behavior.
10. **Sync** status and handoff; do not publish without permission.

Debugging is available at any stage. Tiny changes may use a lighter path; high-risk changes should use the full sequence.

## Approval gates
Ask before material scope expansion, consequential product/architecture decisions, destructive operations, meaningful dependency/licensing changes, risky data migrations, security-control changes, production actions, or publishing externally.

## Principles
- Repository-specific instructions and conventions take precedence over generic examples here.
- Separate confirmed facts from assumptions.
- Preserve unrelated user changes and inspect git status before editing.
- Never hard-code or expose secrets; never use production credentials or real customer data in tests.
- Never weaken security checks or tests merely to get a green result.
- No commit, push, deployment, release, or PR unless explicitly authorized.
- Report exact checks run, outcomes, blocked checks, limitations, and unresolved risks.

## Definition of done
Acceptance criteria are met or unmet items are explicit; relevant checks were run and honestly reported; the diff is focused and reviewed; relevant docs are updated; remaining risks and next steps are clear.

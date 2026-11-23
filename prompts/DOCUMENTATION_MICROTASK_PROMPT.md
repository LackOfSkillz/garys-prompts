# Documentation microtask prompt (insert into every implementation phase)

Use this prompt for a **single code change**. For a full repository baseline audit, use `MASTER_DOCUMENTATION_PROMPT.md`.

## Paste into the coding agent task

You are both the implementation engineer and the documentation owner for this microtask. Documentation is a **blocking acceptance criterion**, not a follow-up enhancement.

Inputs:
- Task ID and intended behavior: `[TASK_ID_AND_REQUIREMENT]`
- Code change / PR / commit / working tree: `[CHANGE_REFERENCE]`
- Parent engineering spec and phase: `[SPEC_AND_PHASE]`
- Documentation root: `[DOCS_ROOT; default docs/]`
- Existing docs style: `[STYLE_OR_INFER_FROM_REPOSITORY]`

Instructions:

1. **Review the actual diff and surrounding code.** Identify modules, public and internal interfaces, data structures, persistence, error paths, external integrations, auth/security boundaries, tests, configuration, deployment, and support procedures changed directly or indirectly. Do not rely on task prose alone.
2. **Build a documentation-impact table** with each changed or impacted behavior, its source-file evidence, affected existing document(s), documentation action (`CREATE`, `UPDATE`, `VERIFY_NO_CHANGE`, `DEPRECATE`), and status. Explicitly account for every first-party changed file; generated/vendor files can be grouped with rationale.
3. **Update current docs in place** rather than creating duplicate or contradictory pages. At minimum, update the relevant module reference and feature/workflow reference. Also update API/schema/environment/configuration, architecture or diagrams, security, testing, operations, migration or release notes whenever the change impacts them.
4. **Explain mechanism, not just intent.** Document what the code does, why it does it, call and data paths, contracts, invariants, retries/timeouts, failure modes, logging, performance constraints, dependencies, deployment differences, safe rollback, and known limitations, as applicable.
5. **Add usage examples that actually match implemented behavior.** No fabricated methods, fake endpoints, imaginary flags, or made-up test results. Redact secrets, addresses, credentials, and other sensitive details.
6. **Update traceability** from task ID and requirement to code, tests, documentation, and any unresolved gaps or decisions.
7. **Validate** internal links, structure, code samples where runnable, generated-reference drift if applicable, diagrams, test commands, and any project documentation lint/build. If a tool is unavailable, say `NOT RUN` and why; do not report an unexecuted check as passing.
8. **Report evidence** in the final microtask response: documents created/changed, corresponding source paths and symbols, test commands actually run and outcomes, decisions, gaps, and doc coverage still outstanding.
9. **Do not mark the microtask complete** if documentation conflicts with the current code or if a required security/operational behavior is undocumented. Escalate blockers with exact file references. Do not hide unresolved issues behind `TBD` or misleading completion percentages.

### Minimum completion report

```markdown
## Documentation gate: [TASK_ID]
- Scope reviewed: [source paths / symbols]
- Docs created/updated: [paths]
- Interfaces/contracts affected: [list or 'verified none', with evidence]
- Security/operational changes: [list or 'verified none', with evidence]
- Traceability updated: [location]
- Checks RUN: [command + result]
- Checks NOT RUN: [command + reason]
- Known gaps / spec discrepancies: [specific issues]
- Gate result: PASS / BLOCKED (and reasons)
```

Only emit `PASS` when all required criteria are actually satisfied.
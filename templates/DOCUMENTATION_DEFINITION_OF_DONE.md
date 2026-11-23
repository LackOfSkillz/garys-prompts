# Documentation definition of done (DoD)

Attach this gate to every coding microtask, PR template, or phase acceptance checklist. A reviewer should be able to verify every checked item against code, docs, or command output.

## Scope and traceability

- [ ] Every changed first-party source/config/schema/test file has been considered in the documentation-impact matrix.
- [ ] Every added/changed user-visible feature has a discoverable feature or workflow reference.
- [ ] Every changed first-party module/package has an up-to-date module reference or explicitly justified grouping.
- [ ] Public interface and versioned contract changes have examples, compatibility notes, and error semantics.
- [ ] Requirement/task IDs link to source, test evidence, and docs; discrepancies are tracked.

## Technical correctness

- [ ] Architecture, dependencies, deployment, data flow, and state transitions reflect current code.
- [ ] Meaningful error modes, retries, fallbacks, idempotency, boundaries, and constraints are documented.
- [ ] Config names, defaults, overrides, environment variables, CLI flags, routes, and response shapes are checked against real source.
- [ ] Code snippets are syntactically valid or explicitly identified as pseudocode and are safe to run.
- [ ] No claimed tests, version support, performance figures, or completion states lack evidence.

## Operations and security

- [ ] Authentication/authorization, trust boundaries, data classification, and security implications have been reviewed when relevant.
- [ ] Docs contain no secrets, real credentials, tokens, private keys, exposed personal data, or unapproved internal topology/IPs.
- [ ] Setup, deployment, upgrades, monitoring, failures, recovery, rollback, backups, and troubleshooting are current where affected.
- [ ] Risks, known limitations, planned features, and unsupported workflows are clearly distinguished from implemented behavior.

## Validation and handoff

- [ ] Existing docs have been updated instead of contradicted by new documents.
- [ ] Docs build/lint, link checking, generated-reference checks, and applicable code-example validation have been run or explicitly marked `NOT RUN`.
- [ ] Mermaid/diagram syntax and links between diagrams and source references have been checked.
- [ ] A fresh engineer can follow at least one realistic end-to-end user or operational journey through the docs.
- [ ] The final report lists files changed, source evidence, validations, unresolved gaps, and `PASS` or `BLOCKED`.

**Gate:** All applicable items must pass. Mark non-applicable items `N/A` with a reason and evidence; never quietly skip them. If a required item fails, the documentation gate is `BLOCKED`.
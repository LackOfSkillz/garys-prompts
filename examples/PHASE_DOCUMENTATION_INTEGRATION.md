# Example: documentation integrated into the engineering phase plan

## Phase 04: Implement a network monitor (example only)

- `P04-M01` Define monitor contracts, schemas, configuration model, and acceptance tests.
- `P04-M02` Implement polling and bounded timeout/backoff behavior.
- `P04-M03` Add permissions, audit logging, and safe credential handling.
- `P04-M04` Implement dashboards, alerts, and accessibility checks.
- `P04-M05` Add integration, failure-path, and configuration tests.
- `P04-M06` **Documentation gate:** apply `DOCUMENTATION_MICROTASK_PROMPT.md` to each preceding microtask; reconcile module, feature, contract, data flow, security, test, runbook, and traceability references; validate diagrams and links.
- `P04-M07` Phase acceptance review: documentation DoD, evidence, discrepancies, operational drill, release notes, and handoff.

## Required microtask fields

```yaml
id: P04-M06
name: Network monitor documentation and handoff
spec_reference: SPEC-04
source_scope:
  - service/monitor
  - ui/monitor
  - config/monitor
  - tests/monitor
artifacts:
  - docs/modules/network-monitor.md
  - docs/features/network-monitoring.md
  - docs/operations/network-monitor-runbook.md
  - docs/architecture/monitor-data-flow.md
  - docs/reference/traceability.md
acceptance_criteria:
  - All current entry points, configuration and contracts verified against source
  - At least one success, timeout and failure journey documented
  - Security boundaries and redacted diagnostic workflow reviewed
  - Documentation gate reports PASS with checks actually run
blocked_if:
  - Undocumented changed API or schema contract
  - Contradiction between code and docs
  - Sensitive values or unverified claims in documentation
```

## Rule for every other phase

Do not reserve all documentation until the last phase. Each implementation microtask must update affected docs, and a phase-close microtask must audit integration and end-to-end behavior. A separate release-readiness pass checks the entire project after changes accumulate.
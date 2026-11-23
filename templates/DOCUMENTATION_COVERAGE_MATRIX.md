# Documentation coverage and traceability matrix template

Keep this matrix machine-readable when practical (e.g., CSV or YAML), and generate a human-readable summary. The matrix is a **discovery ledger**, not a substitute for real documentation.

## Source coverage

| Source path / symbol | Kind | Owner / responsibility | Runtime entry point | Documentation path | Evidence | Status | Gap / next action |
|---|---|---|---|---|---|---|---|
| `src/example/service.py::ExampleService.run` | module + critical method | Example processing | `api/example` | `docs/modules/example-service.md` | code review + test | VERIFIED | None |
| `config/example.yaml` | deployment config | Example defaults | startup | `docs/operations/configuration.md` | parser/source | PENDING | Confirm precedence |

Possible statuses: `DISCOVERED`, `DRAFTED`, `VERIFIED`, `OUT_OF_DATE`, `BLOCKED`, `DEFERRED_WITH_REASON`.

## Feature to source to test to documentation

| Requirement / feature ID | Expected behavior | Implemented source | Evidence/test | User-facing or operator doc | Gaps / mismatches |
|---|---|---|---|---|---|
| `FEAT-001` | Example feature contract | `src/example` | `tests/example_test.py` | `docs/features/example.md` | None |

## Interface inventory

| Interface | Caller / consumer | Contract source | Auth/trust boundary | Reference doc | Compatibility notes |
|---|---|---|---|---|---|
| `GET /example` | web client | `src/api/example.py` | auth middleware | `docs/api/http.md` | v1 stable |

## Required summaries

- Inventory counts by source category and by documentation state.
- Every uncovered critical path and its operational or security risk.
- Every documented-but-nonexistent symbol/route/feature discovered.
- Every spec-vs-code mismatch; do not silently classify as completed.
- Every intentionally undocumented generated/vendor file and why.
- Verification timestamp, repository commit SHA, and agent/tool limitations.

**Avoid a misleading score:** Percentages may be given for _accounted-for source inventory_, but completeness is also gated by human review of behavioral accuracy, security, and operability. A row marked `VERIFIED` needs a factual evidence anchor, not just the existence of a Markdown file.
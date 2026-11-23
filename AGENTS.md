# Instructions for coding agents working in Gary's Prompts

This repository is a maintained library of reusable engineering prompts, not an application codebase.

## Authoring rules

1. Preserve platform-neutral wording unless a prompt explicitly targets a specific tool.
2. Keep the master documentation prompt comprehensive but grounded: an agent must never invent repository facts or report tests it did not execute.
3. Use clear separation between implemented features, intended design, unverified assumptions, and future work.
4. Every prompt should specify required inputs, ordered actions, concrete deliverables, validation, acceptance criteria, and blocker behavior.
5. Prefer reusable templates over project-specific guesses. Demonstration paths, credentials, hosts, APIs, and IDs must be clearly synthetic.
6. Update `README.md` if prompts are added, renamed, retired, or materially changed.
7. Maintain the microtask and definition-of-done prompts when the master prompt changes its acceptance policy.
8. Validate Markdown links and internal cross-file references before committing.
9. Never put real credentials, sensitive infrastructure identifiers, personal data, or secrets in this repository.
10. Do not change or weaken a documentation quality gate without explicitly explaining the change in the PR.

## Key files

- `prompts/MASTER_DOCUMENTATION_PROMPT.md`: authoritative prompt for full documentation investigations.
- `prompts/DOCUMENTATION_MICROTASK_PROMPT.md`: compact per-change documentation gate.
- `templates/DOCUMENTATION_DEFINITION_OF_DONE.md`: reviewer acceptance checklist.
- `templates/DOCUMENTATION_COVERAGE_MATRIX.md`: source and traceability ledger format.
- `examples/PHASE_DOCUMENTATION_INTEGRATION.md`: phase/microtask integration example.

## Validation checklist for this repository

- Verify local Markdown links and referenced file paths.
- Check that examples use synthetic values and no credential material.
- Check that each documented behavior is compatible with the master prompt.
- Record exactly what was checked, and do not claim unavailable checks passed.
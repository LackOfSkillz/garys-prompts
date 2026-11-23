# Gary's Prompts

A reusable, agent-neutral library of engineering prompts for taking software projects from brainstorming to engineering specifications, implementation phases, atomic microtasks, verified documentation, and maintainable handoff.

**Repository slug:** `garys-prompts` (GitHub-safe spelling of "Gary's Prompts")

## Start here

| Use case | File | When to use |
| --- | --- | --- |
| Audit and document an entire application | [`prompts/MASTER_DOCUMENTATION_PROMPT.md`](prompts/MASTER_DOCUMENTATION_PROMPT.md) | At project bootstrap, major release, or documentation catch-up |
| Document one implementation microtask | [`prompts/DOCUMENTATION_MICROTASK_PROMPT.md`](prompts/DOCUMENTATION_MICROTASK_PROMPT.md) | In every engineering phase and every feature PR |
| Require documentation during a code review | [`templates/DOCUMENTATION_DEFINITION_OF_DONE.md`](templates/DOCUMENTATION_DEFINITION_OF_DONE.md) | Acceptance gate for all completed work |
| Plan and trace source-to-document coverage | [`templates/DOCUMENTATION_COVERAGE_MATRIX.md`](templates/DOCUMENTATION_COVERAGE_MATRIX.md) | Discover missing modules, APIs, and operational procedures |
| See a phase/microtask integration pattern | [`examples/PHASE_DOCUMENTATION_INTEGRATION.md`](examples/PHASE_DOCUMENTATION_INTEGRATION.md) | When producing engineering blueprints and task lists |
| Publish the repository | [`PUBLISH_TO_GITHUB.md`](PUBLISH_TO_GITHUB.md) | For initial upload to your GitHub account |

## Philosophy

The documentation is a maintained engineering deliverable, not an optional last step. A feature is not complete until an unfamiliar engineer can understand its purpose, interfaces, data flow, security boundaries, failure behavior, test evidence, configuration, operational impact, and limitations **from current documentation backed by current code**.

The source code is authoritative for **implemented behavior**. The engineering specification is authoritative for **intended behavior**. Any difference must be explicitly recorded as a specification/implementation discrepancy, not quietly reconciled by inventing claims.

## How to use the master prompt

1. Give a coding agent access to the target source repository and, if available, the engineering blueprint, phase backlog, CI output, and architecture decisions.
2. Copy the complete contents of `prompts/MASTER_DOCUMENTATION_PROMPT.md` into the agent session.
3. Set or supply the target repo, documentation destination, desired mode (`BASELINE_AUDIT`, `INCREMENTAL_CHANGE`, or `RELEASE_READINESS`), scope, and constraints. The defaults in the prompt are safe when omitted.
4. Require the agent to follow its reconnaissance, coverage matrix, documentation writing, validation, and final evidence report in order.
5. Review discrepancies and blockers before accepting the resulting documentation PR.

## Suggested project documentation layout

The target application's docs may use its own existing conventions. When there is no convention, the master prompt defines an adaptable `docs/` layout with architecture, modules, features, APIs, data, security, operation/runbooks, testing, decisions, and traceability.

## Agent portability

Designed for Claude Code, OpenAI Codex, Aedan or other local coding agents, and editor-based assistants. The prompt does not rely on any proprietary tool. Agents should use the repository's existing tools and never imply they ran commands or inspected files that they could not access.

## Scope and safety

No real credentials, secrets, private keys, access tokens, customer data, sensitive IP addresses, or production infrastructure details should be copied into documentation. Security-sensitive architecture must be documented at a level approved by the repository owner. Use safe placeholders and record controlled-document locations where necessary.

## Future library entries

This repository starts with the documentation system. Additional versioned prompts can be added for brainstorming, engineering specifications, architecture reviews, phase planning, microtask creation, coding, testing, release engineering, and security reviews.
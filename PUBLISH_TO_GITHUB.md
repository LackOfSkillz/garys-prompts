# GitHub Publication

This repository has been published at https://github.com/LackOfSkillz/garys-prompts.

## Updating the prompt library

1. Clone the repository: `git clone https://github.com/LackOfSkillz/garys-prompts.git`.
2. Make changes on a new branch, preserving the version information and agent-neutral design.
3. Update relevant tests, checklists, and usage examples when documentation policy changes.
4. Open a pull request using the provided template; verify the instructions are complete and do not expose secrets.
5. Merge the reviewed changes to `main`.

## Getting started

- Full application audit: `prompts/MASTER_DOCUMENTATION_PROMPT.md`
- Per-microtask documentation: `prompts/DOCUMENTATION_MICROTASK_PROMPT.md`
- Documentation completion gate: `templates/DOCUMENTATION_DEFINITION_OF_DONE.md`

The repository itself is a prompt library. Applying these prompts to another project requires giving the coding agent access to that other project's source and task context.

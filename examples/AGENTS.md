# Agent instructions, example project

Read and follow these local files before editing code:

- `docs/guardrails/rules/testing.md`
- `docs/guardrails/rules/debugging.md`
- `docs/guardrails/rules/evidence.md`
- `docs/guardrails/rules/change-safety.md`

These paths assume that the adopted files have been copied into `docs/guardrails/` in this repository. A reference to a remote URL alone does not import its contents.

## Explicit local policies

For EAG-TEST-001, obtain the owner's approval before modifying any existing test. First identify the exact conflict and proposed edit.

For EAG-TEST-002, maintain 100% statement and branch coverage in the canonical suite. Do not change coverage exclusions or thresholds to make a change pass.

## Project gates

Replace this section with the repository's real commands and the source of each gate result. Do not claim these sample policies are active until they have been adopted by the project.

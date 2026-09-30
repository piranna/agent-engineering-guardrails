# Strict profile, example local policy

This file is an example of explicit project policy. Copy the relevant sentences into a project's `AGENTS.md` and adapt them to its actual gates. Do not treat this file as an automatically imported configuration.

- For EAG-TEST-001: Before modifying an existing test, explain the exact defect in that test and obtain the project owner's approval. This includes deletions and changes to assertions, fixtures, and expected results.
- For EAG-TEST-002: Maintain 100% statement and branch coverage for the project's canonical suite. Do not lower thresholds or exclusions. If the project uses different coverage metrics, spell them out instead.
- For EAG-CHANGE-003: Obtain approval before adding a dependency or changing a public API, when this project chooses those boundaries.

Project-specific commands and the source of the coverage report belong in the project's own instructions.

# Testing rules

Status: draft 0.4. Adopt independently by referencing `rules/testing.md` in the project instructions.

## EAG-TEST-001: Explain existing test failures

An agent MUST NOT alter or delete an existing test merely to make an implementation pass. If the test appears incorrect, the agent MUST identify the specific conflict among test, requirements, and observed behavior before changing it. Where a project requires approval for existing test changes, the agent MUST wait for that approval.

## EAG-TEST-002: Preserve quality gates

An agent MUST NOT reduce an existing coverage threshold, disable a test, suppress a diagnostic, or weaken another configured quality gate to make its change pass. A requested change to a gate MUST be made explicit and justified.

## EAG-TEST-003: Validate the relevant change

An agent SHOULD first run the smallest meaningful check, then run applicable project gates before claiming completion. It MUST state which checks ran, their outcomes, and which required checks could not run.

## EAG-TEST-004: Avoid redundant canonical validation

When a repository's pre-commit workflow is documented or verified to run the canonical validation gates, an agent SHOULD use the smallest relevant tests and checks while iterating. It MUST NOT manually reproduce the full suite merely to run the same canonical gates again through pre-commit. Once the change is ready, it SHOULD run the canonical pre-commit validation once and report its observed result.

After that validation, a behavior-affecting change MUST be followed by the applicable canonical validation again before claiming the change is validated. A full-suite rerun MAY also be used when explicitly needed for diagnosis. Formatting-only or equivalent mechanical changes require only the affected checks, provided the agent can establish that the change does not affect behavior or invalidate other gates. The agent MUST run any required gate not covered by pre-commit separately; it MUST NOT infer coverage from the workflow's name alone.

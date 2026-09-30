# Testing rules

Status: draft 0.6. Adopt independently by referencing `rules/testing.md` in the project instructions.

## EAG-TEST-000: Read applicable agent instructions first

Before implementing a change, an agent MUST read the applicable `AGENTS.md` files and the local rule files they explicitly adopt, when those files are available. It MUST identify the repository's relevant validation workflow before choosing tests. If an expected instruction file is unavailable, it MUST say so rather than assume its contents.

## EAG-TEST-001: Explain existing test failures

An agent MUST NOT alter or delete an existing test merely to make an implementation pass. If the test appears incorrect, the agent MUST identify the specific conflict among test, requirements, and observed behavior before changing it. Where a project requires approval for existing test changes, the agent MUST wait for that approval.

## EAG-TEST-002: Preserve quality gates

An agent MUST NOT reduce an existing coverage threshold, disable a test, suppress a diagnostic, or weaken another configured quality gate to make its change pass. A requested change to a gate MUST be made explicit and justified.

## EAG-TEST-003: Validate the relevant change

An agent SHOULD first run the smallest meaningful check, then run applicable project gates before claiming completion. It MUST state which checks ran, their outcomes, and which required checks could not run.

## EAG-TEST-004: Avoid redundant canonical validation

When a repository's pre-commit workflow is documented or verified to run the canonical validation gates, an agent SHOULD use the smallest relevant tests and checks while iterating. It MUST NOT manually reproduce the full suite merely to run the same canonical gates again through pre-commit. Once the change is ready, it SHOULD run the canonical pre-commit validation once and report its observed result.

After that validation, a behavior-affecting change invalidates the result for the changed code; the agent MUST complete applicable canonical validation again before claiming the changed code is validated, following EAG-TEST-005 for when to rerun it. A full-suite rerun MAY also be used when explicitly needed for diagnosis. Formatting-only or equivalent mechanical changes require only the affected checks, provided the agent can establish that the change does not affect behavior or invalidate other gates. The agent MUST run any required gate not covered by pre-commit separately; it MUST NOT infer coverage from the workflow's name alone.

## EAG-TEST-005: Return to focused checks after full-validation failures

After a failed or incomplete full validation, an agent MUST NOT rerun it immediately after each fix. It MUST return to focused validation, review all known failures and affected call sites, and complete the related implementation and code review before another full run. It SHOULD rerun full validation when the implementation is believed final. A behavior-affecting edit after a full run invalidates that result for the edited code, but does not by itself justify an immediate full rerun. A full run MAY be used earlier when explicitly needed to diagnose an issue that focused checks cannot resolve.

## EAG-TEST-006: Do not iterate using the complete pytest suite

In projects that use pytest, an agent MUST run only tests related to the changed behavior during iteration. It MUST NOT use the complete pytest suite as a discovery, debugging, or iterative development loop. After a full-suite run exposes an issue, it MUST return to focused tests until the known issues, implementation work, and code review are complete. It SHOULD then run the complete suite through the applicable pre-push or final canonical validation, if that workflow requires it. An explicit user request or a diagnostic need that focused checks cannot resolve MAY justify an earlier full-suite run. The agent MUST NOT skip any separately required gate.

## EAG-TEST-007: Match validation to nonbehavioral changes

A change limited to documentation, formatting, comments, or static metadata does not by itself justify running the complete test suite. An agent SHOULD run only checks affected by that change, after verifying that it cannot affect generated artifacts, runtime behavior, test discovery, packaging, or another required gate. If such an effect is plausible, the agent MUST validate the affected behavior or gate. An explicit project or user requirement for full validation still applies.

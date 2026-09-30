# Testing rules

Status: draft 0.1. Adopt independently by referencing `rules/testing.md` in the project instructions.

## EAG-TEST-001: Explain existing test failures

An agent MUST NOT alter or delete an existing test merely to make an implementation pass. If the test appears incorrect, the agent MUST identify the specific conflict among test, requirements, and observed behavior before changing it. Where a project requires approval for existing test changes, the agent MUST wait for that approval.

## EAG-TEST-002: Preserve quality gates

An agent MUST NOT reduce an existing coverage threshold, disable a test, suppress a diagnostic, or weaken another configured quality gate to make its change pass. A requested change to a gate MUST be made explicit and justified.

## EAG-TEST-003: Validate the relevant change

An agent SHOULD first run the smallest meaningful check, then run applicable project gates before claiming completion. It MUST state which checks ran, their outcomes, and which required checks could not run.

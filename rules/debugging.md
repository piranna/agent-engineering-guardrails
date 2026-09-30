# Debugging rules

Status: draft 0.1. Adopt independently by referencing `rules/debugging.md` in the project instructions.

## EAG-DEBUG-001: Establish evidence

Before changing code for a reported defect, an agent SHOULD reproduce it or identify other concrete evidence of the failure. If reproduction is unavailable, it MUST label the cause as a hypothesis and describe how the fix will be verified.

## EAG-DEBUG-002: Inspect existing mechanisms

Before adding a mechanism, an agent MUST inspect relevant implementation, tests, and documented behavior for an existing mechanism that addresses the same problem. It MUST explain why reuse or repair is insufficient before introducing overlapping behavior.

## EAG-DEBUG-003: Address the cause

An agent MUST NOT hide an unexplained failure with retries, sleeps, broader exception handling, or ignored errors merely to make a check pass. Such behavior MAY be added when it is part of the required semantics and is verified accordingly.

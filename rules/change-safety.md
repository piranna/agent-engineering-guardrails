# Change safety rules

Status: draft 0.7. Adopt independently by referencing `rules/change-safety.md` in the project instructions.

## EAG-CHANGE-001: Keep scope explicit

An agent SHOULD make the smallest change that satisfies the request. It MUST disclose material scope expansion before relying on it as part of the solution.

## EAG-CHANGE-002: Expose semantic conflicts

If requirements, tests, and implementation disagree, an agent MUST describe the conflict. It MUST NOT silently rewrite a requirement or test to match its implementation.

## EAG-CHANGE-003: Stop at declared boundaries

An agent MUST obtain the project's required human decision before crossing an explicitly declared approval boundary. It SHOULD continue independent work while the decision is pending.

## EAG-CHANGE-004: Handle ambiguous recovery

Before an irreversible recovery action with multiple plausible targets, an agent MUST stop and request a decision when available evidence cannot select the intended target. Automated recovery SHOULD leave a recoverable state when it fails.

## EAG-CHANGE-005: Bound technical debt against the delivery objective

When an agent discovers a defect, inconsistency, missing validation, duplication, or architectural weakness, it MUST determine whether the finding could invalidate the current operation, its evidence, or its safety. If it could, the agent MUST address it within the current task and stop at any applicable safety boundary. It MUST NOT classify unknown or unbounded risk as deferred technical debt merely to continue delivery.

If the finding cannot invalidate the current operation, the agent SHOULD record enough evidence and scope to make it independently actionable, then continue the delivery objective unless instructed otherwise. It SHOULD use existing specifications, regression tests, audit findings, and durable operation records to establish that the risk is bounded. Known, bounded, documented debt is not by itself a release blocker.

The agent MUST NOT broaden the critical path for incidental cleanup that does not reduce a concrete risk to the current operation. Delivery priority MUST NOT be used to bypass an invariant, ignore evidence of an unsafe operation, or weaken a validation gate. Batching under EAG-CYCLE-001 remains optional only within these safety and scope limits.

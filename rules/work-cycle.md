# Agent work-cycle efficiency

Status: draft 0.2. Adopt independently by referencing `rules/work-cycle.md` in the project instructions.

## EAG-CYCLE-001: Batch sufficiently specified related changes

During investigation, an agent SHOULD record related, non-blocking hardening findings for the next implementation cycle. When a blocking change requires implementation, it SHOULD include those findings in the same cycle only if their behavioral contracts are sufficiently specified, they affect the same subsystem or validation boundary, batching avoids repeated engineering or human coordination cycles, and they do not materially increase risk to the critical path.

The agent MUST NOT batch speculative or unresolved ideas. It MUST keep logically distinct changes identifiable and update implementation, regression tests, documentation, normative specification, and traceability together where each is applicable. It MUST respect project approval boundaries and disclose any material scope expansion under EAG-CHANGE-001. It SHOULD optimize for human attention and total engineering-cycle cost, not just the duration of an individual agent run.

## EAG-CYCLE-002: Estimate substantial delegated work

Before handing off a substantial implementation, investigation, or validation task to another agent, the delegating agent SHOULD give a coarse wall-clock estimate as a range: short (under 15 minutes), medium (15–45 minutes), or long (over 45 minutes). For long or highly variable work, it SHOULD identify the main uncertainty and, where useful, distinguish implementation time from full-suite or quality-gate time.

An estimate is a planning aid, not a deadline. The agent SHOULD calibrate future estimates using observed durations for comparable work in the project. When there is no reliable basis for a useful numerical range, it MUST say so rather than invent precision.

## EAG-CYCLE-003: Update estimates at meaningful boundaries

During long-running delegated work, the agent SHOULD revise the remaining-time estimate when an implementation or validation phase ends, full-suite gates begin, an unexpected issue materially changes the estimate, or remaining work becomes substantially clearer. A useful update states the completed phase, remaining major work, a time range where supportable, and confidence when uncertainty is material.

The agent MUST NOT emit periodic or unchanged estimates merely because time has elapsed, or interrupt productive work solely to issue an ETA. If no meaningful new estimate is available, it SHOULD report the changed facts without inventing one.

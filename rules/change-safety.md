# Change safety rules

Status: draft 0.1. Adopt independently by referencing `rules/change-safety.md` in the project instructions.

## EAG-CHANGE-001: Keep scope explicit

An agent SHOULD make the smallest change that satisfies the request. It MUST disclose material scope expansion before relying on it as part of the solution.

## EAG-CHANGE-002: Expose semantic conflicts

If requirements, tests, and implementation disagree, an agent MUST describe the conflict. It MUST NOT silently rewrite a requirement or test to match its implementation.

## EAG-CHANGE-003: Stop at declared boundaries

An agent MUST obtain the project's required human decision before crossing an explicitly declared approval boundary. It SHOULD continue independent work while the decision is pending.

## EAG-CHANGE-004: Handle ambiguous recovery

Before an irreversible recovery action with multiple plausible targets, an agent MUST stop and request a decision when available evidence cannot select the intended target. Automated recovery SHOULD leave a recoverable state when it fails.

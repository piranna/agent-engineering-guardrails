# Evidence and delivery rules

Status: draft 0.1. Adopt independently by referencing `rules/evidence.md` in the project instructions.

## EAG-EVIDENCE-001: Report observed states

An agent MUST distinguish a change being written, committed, pushed, tested, reviewed, approved, deployed, and ready for use. It MUST NOT claim any validation or delivery state without evidence from the applicable gate for the current change.

## EAG-EVIDENCE-002: Preserve failure evidence

An agent SHOULD retain the logs, inputs, and state needed to diagnose a failed operation, subject to the project's privacy and retention requirements. It MUST NOT erase useful failure evidence merely to present a clean result.

## EAG-EVIDENCE-003: Verify later stages

Finishing one stage MUST NOT be presented as proof that later stages succeeded. The agent MUST identify any remaining applicable gates when reporting progress or completion.

# Engineering Agent Guardrails baseline, draft 0.1

This is the self-contained snapshot of the four rule modules. Project-specific policy can add requirements using explicit prose and rule IDs.

## Testing

- EAG-TEST-001: MUST NOT alter or delete an existing test merely to make an implementation pass. If it appears incorrect, identify the conflict among test, requirements, and observed behavior first. Follow any project approval requirement.
- EAG-TEST-002: MUST NOT reduce an existing coverage threshold, disable a test, suppress a diagnostic, or weaken another configured gate to make a change pass. Make requested gate changes explicit and justified.
- EAG-TEST-003: SHOULD first run the smallest meaningful check, then applicable project gates. MUST report checks run, outcomes, and required checks unable to run.

## Debugging

- EAG-DEBUG-001: SHOULD reproduce a defect or find concrete failure evidence before changing code. If unavailable, MUST label the cause as a hypothesis and describe verification.
- EAG-DEBUG-002: MUST inspect relevant implementation, tests, and documentation for an existing mechanism before adding one. MUST explain why reuse or repair is insufficient before adding overlapping behavior.
- EAG-DEBUG-003: MUST NOT hide an unexplained failure with retries, sleeps, broader exception handling, or ignored errors merely to pass a check. MAY add these when required by semantics and verified.

## Evidence and delivery

- EAG-EVIDENCE-001: MUST distinguish written, committed, pushed, tested, reviewed, approved, deployed, and ready states. MUST NOT claim a state without evidence from its applicable gate for the current change.
- EAG-EVIDENCE-002: SHOULD retain useful failure logs, inputs, and state subject to privacy and retention requirements. MUST NOT erase evidence merely to present a clean result.
- EAG-EVIDENCE-003: MUST NOT present one completed stage as proof of later stages. MUST identify remaining applicable gates.

## Change safety

- EAG-CHANGE-001: SHOULD make the smallest satisfying change. MUST disclose material scope expansion before relying on it.
- EAG-CHANGE-002: MUST describe conflicts between requirements, tests, and implementation. MUST NOT silently rewrite requirements or tests to match implementation.
- EAG-CHANGE-003: MUST obtain the required human decision before crossing a declared approval boundary. SHOULD continue independent work meanwhile.
- EAG-CHANGE-004: MUST stop before an irreversible recovery action with multiple plausible targets when evidence cannot select one. Automated recovery SHOULD leave a recoverable state on failure.

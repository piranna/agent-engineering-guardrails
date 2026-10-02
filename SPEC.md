# Engineering Agent Guardrails, draft 0.8

## Scope

These rules govern how a coding agent changes and validates a software project. They do not replace the project's requirements, user instructions, or platform safety rules.

## Normative terms

**MUST** is mandatory when the rule is adopted. **MUST NOT** prohibits an action. **SHOULD** is the default unless a concrete reason for an exception is stated. **MAY** permits an action.

## Adoption

A project MUST list the rule files it adopts, or include their full text in its agent instructions. A rule applies only when its text is available to the agent in the current workspace or has been explicitly retrieved. A URL alone is a pointer, not a reliable import mechanism.

Each `rules/*.md` file is independently adoptable. The baseline distribution adopts all five rule files. Projects MAY adopt a subset by listing paths and MUST state any local additions in plain language. A profile is an example of local additions, not a hidden parameter format.

If instructions conflict, follow the applicable higher-priority user and platform instructions. For conflicts within the adopted project material, the project's explicit local override controls the general rule only where it identifies the rule and the intended exception. If conflict or scope remains unclear, surface it before taking a consequential action.

## Verification and releases

Never claim a gate passed unless its result was observed for the relevant change. A version tag should freeze the normative rule texts and the matching distribution snapshot. Changes to behavior require a new version; editorial clarifications should say whether they change behavior.

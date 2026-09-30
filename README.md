# Engineering Agent Guardrails

A small, versioned set of engineering instructions for coding agents. This is a draft, not a claim of conformance to an external standard.

## Start here

1. Read [SPEC.md](SPEC.md) for adoption and precedence.
2. Adopt individual files in `rules/` by copying their full normative text into your repository instructions, or by explicitly instructing an agent to read the local files. A remote link alone does not guarantee retrieval.
3. See [examples/AGENTS.md](examples/AGENTS.md) for local references and [dist/AGENTS.baseline.md](dist/AGENTS.baseline.md) for a self-contained baseline.
4. Record stricter choices in the project `AGENTS.md` using the explicit wording in [profiles/strict.md](profiles/strict.md).

The independently adoptable modules cover [testing](rules/testing.md), [debugging](rules/debugging.md), [evidence](rules/evidence.md), [change safety](rules/change-safety.md), and [agent work-cycle efficiency](rules/work-cycle.md).

No CLI or Markdown preprocessor is required. Each rule file has a stable identifier and is readable independently. Relative Markdown links keep the sources suitable for documentation generators.

## Status

Draft 0.6. Rule identifiers should remain stable; wording and policy choices need review against real projects before a 1.0 release. The distribution file is a manually maintained snapshot of the baseline; update it whenever normative rules change.

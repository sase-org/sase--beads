# Bead: sase-m6.6.1.3 — Generalize the Python reference evaluator

[Bead Pages](../README.md) / [sase-m6.6.1](sase-m6.6.1.md) / sase-m6.6.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.3` · **Size:** medium
**Created:** 2026-08-15 06:17:51 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

python_reference: make query_facade's Python-owned per-row evaluator consume the same compiled profile and typed/coerced Artifact fields as Rust, implement the shared field, sigil, predicate, macro, searchable-text and boolean semantics, and expand cross-language fixtures so the Python reference evaluator and Rust batch evaluator return identical matches and errors for every pane profile.

## Dependencies

- **Depends on:** [sase-m6.6.1.1](sase-m6.6.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.5](sase-m6.6.1.5.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m6.6.1.6](sase-m6.6.1.6.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.3/README.md) | [sase-m6.6.1.3](sase-m6.6.1.3.md) | 0 |

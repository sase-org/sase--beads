# Bead: sase-1ab.1.1 — sase-core additive sase-turn rename (core-expand)

[Bead Pages](../README.md) / [sase-1ab.1](sase-1ab.1.md) / sase-1ab.1.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ab.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ab.1.md) · **Assignee:** `sase-1ab.1.1.land`
**Created:** 2026-09-26 00:28:13 EDT
**Plan:** [202609/sase\_core\_turn\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_turn_expand.md)

## Description

sase-core names the former sase-shell concept with turn and named-proc vocabulary in Rust modules, types, functions, constants, tests, comments, and messages, and registers the two new pyo3 binding names next to the legacy ones. Every renamed input accepts the old and new spellings. Serialized output, schema versions, the SQLite gate_shell_id column, and goldens stay byte-identical, so a sase tree pinned to the previous core, and a sase workspace rebuilt against this core, still passes sase tool run check with no sase source changes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ab.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ab.1.1.land/README.md) | [sase-1ab.1.1](sase-1ab.1.1.md) | 0 |

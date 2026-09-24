# Bead: sase-17m.2.1 — sase-core additive agent-session rename (core-expand)

[Bead Pages](../README.md) / [sase-17m.2](sase-17m.2.md) / sase-17m.2.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.land`
**Created:** 2026-09-23 22:54:49 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

sase-core names the former agent-family concept "agent session" in every Rust module, type, function, constant, enum variant, test, comment, and message, and exposes the new pyo3 binding names next to the legacy ones. Every input accepts both spellings. Serialized output, schema versions, SQLite columns, and goldens stay byte-identical, so a sase tree pinned to the previous core, and every sase workspace that rebuilds against the new core, keeps passing `sase tool run check`.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md) | [sase-17m.2.1](sase-17m.2.1.md) | 0 |

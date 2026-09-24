# Bead: sase-17m.3.1.2 — Canonical agent-session metadata keys and shared accessor

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.2` · **Size:** medium
**Created:** 2026-09-24 02:56:45 EDT · **Closed:** 2026-09-24 05:19:32 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

canonical-keys: make src/sase/plan_chain.py own AGENT_SESSION_* keys, the separator, and LEGACY_AGENT_FAMILY_* constants read only by one shared accessor. Route every agent_meta.json / done.json reader through it and make every writer emit only agent_session, agent_session_role, and agent_session_shell, dropping legacy keys on rewrite.

## Notes

[2026-09-24T09:18:46Z · sase-17m.3.1.2] PROPOSED FOLLOW-UP: wire-mirrors removes the with_legacy_agent_session_keys bridge in src/sase/core/wire.py when AgentMetaWire/DoneMarkerWire fields rename to agent_session spellings

[2026-09-24T09:19:32Z · sase-17m.3.1.2] canonical-keys done: plan_chain owns AGENT_SESSION_* keys/separator, LEGACY_AGENT_FAMILY_* consts, new-then-legacy accessors, set/strip writer helpers, renamed helpers with deprecated aliases; ~35 reader files routed through accessors; writers (promotion, directive metadata, followup artifacts, inventory, reclaim, wait classify) emit new keys only; family_shell_from_mapping reads new key first; with_legacy_agent_session_keys bridge keeps legacy wire fields hydrating (wire-mirrors removes it). Verified: new tests/test_plan_chain_agent_session_keys.py (17 pass); updated writer-output assertions to new keys + no-legacy checks; fmt/ruff/mypy/keep-sorted/flags/pyscripts/test-waits/changelog/patch-stitch gates pass; ~1000 targeted tests green (monitor/gate/shells/axe/agents_sync/agent/ace/fakey). Pre-existing on clean HEAD, left untouched: symvision 73 errors repo-wide, completion bead-candidates test; fixed incidentally one pre-existing mypy error in file_panel/_content.py that blocked the gate

## Dependencies

- **Depends on:** [sase-17m.3.1.1](sase-17m.3.1.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.3](sase-17m.3.1.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.2/README.md) | [sase-17m.3.1.2](sase-17m.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29ca9ee`](https://github.com/sase-org/sase/commit/29ca9ee46fde78dee5b96a48c9021101b608624e) | refactor(agent-session): canonical metadata keys and shared accessor (sase-17m.3.1.2) | [sase-17m.3.1.2](sase-17m.3.1.2.md) | 2026-09-24 05:21:50 EDT |

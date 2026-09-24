# Bead: sase-17m.2.1 — sase-core additive agent-session rename (core-expand)

[Bead Pages](../README.md) / [sase-17m.2](sase-17m.2.md) / sase-17m.2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.land`
**Created:** 2026-09-23 22:54:49 EDT · **Closed:** 2026-09-24 02:48:23 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

sase-core names the former agent-family concept "agent session" in every Rust module, type, function, constant, enum variant, test, comment, and message, and exposes the new pyo3 binding names next to the legacy ones. Every input accepts both spellings. Serialized output, schema versions, SQLite columns, and goldens stay byte-identical, so a sase tree pinned to the previous core, and every sase workspace that rebuilds against the new core, keeps passing `sase tool run check`.

## Notes

[2026-09-24T06:48:23Z · sase-17m.2.1.land] Land verified: all 4 phases closed; sase-core commits c5b9c0d/ef82848/b814a0f/ae9dbf6 (on origin/master) + sase companion a764a76d4. Spot-checked: agent_family.rs->agent_session.rs, fleet_family.rs->fleet_agent_session.rs; 4 new pyo3 names registered beside 4 legacy wrappers (identity, agent_scan, fleet); %id session= with invalid-id-session code; session/sessions reserved; logical_key_matches + fallback-id equivalence tests; legacy constants (LEGACY_AGENT_SESSION_KIND/PAGES_DIR/KEY_SEGMENT) keep emitted strings. Diff 1a2a752..ae9dbf6: no fleet_api_v1.json/contracts change, no SQL schema change, only AGENT_FAMILY_RESOLUTION_WIRE_SCHEMA_VERSION renamed (value 1 unchanged), python_wire_parity.rs identifier-only (key-order asserts intact). Integration: only sase commit since epic start besides a764a76d4 is e662494ba (sase-17m.1 free-name, unrelated to core); no sase-core commits beyond epic; sase-side cutover belongs to sase-17m.3 by design. Follow-ups: wire-cutover items -> DISCOVERED ISSUE note on sase-17m.3; core-contract flips/binding removals -> note on sase-17m.8; tool_run private_argv flake -> new task sase-17n; gateway fleet route flakes -> +1 on sase-15g; mypy _content.py:132 error -> declined, caused by sase-17d.3 (00ee51996) and already recorded as DISCOVERED ISSUE on active epic sase-17d (still reproduces). No epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.land/README.md) | [sase-17m.2.1](sase-17m.2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@f4ede6d`](https://github.com/sase-org/sase--plans/commit/f4ede6dd559c0b0bc69003ba9e615f130e3b8c6f) | chore(plans): mark agent\_session\_core\_expand plan done after sase-17m.2.1 landed | [sase-17m.2.1](sase-17m.2.1.md) | 2026-09-24 03:02:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.3][1] | parent epic plan context | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.3/README.md

<!-- sase:referenced-by:end -->

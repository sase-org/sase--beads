# Bead: sase-1ip.2 — Core autonomy record, compatibility profiles, and evaluate()

[Bead Pages](../README.md) / [sase-1ip](README.md) / sase-1ip.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yj.md) · **Assignee:** `sase-1ip.2` · **Size:** medium
**Created:** 2026-10-09 05:12:52 EDT · **Closed:** 2026-10-09 06:24:33 EDT
**Plan:** [202610/auto\_e1\_autonomy\_record.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_e1_autonomy_record.md)

## Description

core_policy: sase-core autonomy module with the v1 record, policy, request, and decision wires, the %auto compatibility translation, evaluate() over explicit option IDs, the agent-scan field, and the Python bindings.

## Notes

[2026-10-09T10:22:08Z · sase-1ip.2] PROPOSED FOLLOW-UP: Add decisions:autonomy-one-record memory note (autonomy is one record evaluated in core, not gate UI defaults); skipped per epic decision_record=no

[2026-10-09T10:24:33Z · sase-1ip.2] core_policy done: new sase_core autonomy module (v1 record/policy/request/decision wires, 4 compat profiles, resolve via classify_auto_directive, legacy translate+project, evaluate over explicit option IDs, digest golden); agent_scan carries trailing autonomy and derives legacy approve/action from it; fleet_owner_facts auto-approved via evaluate (tier-aware, legacy fallback on unreadable tier); new sase_core_py autonomy bindings (resolve/from_legacy/projection/evaluate/schema_version) with round-trip tests; sase mirror adds trailing autonomy passthrough. Verified: core sase tool run check green (autonomy 19, agent_scan 171+, fleet 10, py bindings 3, new scanner tests); sase sase tool run check STATE succeeded (all lints, validation, escalated full lane). No behavior change: Python gate paths untouched. No memory edits per decision_record=no (PROPOSED FOLLOW-UP noted). No new require_rust_binding call sites so no ratchet needed; host pins core at land. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1ip.3](sase-1ip.3.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1ip.4](sase-1ip.4.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ip.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.2/README.md) | [sase-1ip.2](sase-1ip.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@01b0ad7`](https://github.com/sase-org/sase-core/commit/01b0ad734e7acee14bf5fd88ab12e449540b88f3) | feat(autonomy): add core record, compatibility profiles, and evaluate() | [sase-1ip.2](sase-1ip.2.md) | 2026-10-09 06:37:51 EDT |
| sase | [`9c5000f`](https://github.com/sase-org/sase/commit/9c5000f2dbb126962ea0a84856d0a49115450dc7) | feat(autonomy): carry core-owned autonomy record on AgentMetaWire | [sase-1ip.2](sase-1ip.2.md) | 2026-10-09 07:44:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ip.2][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1ip.land--3][2] | finish_auto_e1_landing closeout: verify all phase children closed and exit criteria met | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ip.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ip.land.md

<!-- sase:referenced-by:end -->

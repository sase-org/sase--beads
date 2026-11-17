# Bead: sase-1t2.11.1.6 — Exercise a real monitor hijack and recovery

[Bead Pages](../README.md) / [sase-1t2.11.1](sase-1t2.11.1.md) / sase-1t2.11.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) · **Assignee:** `sase-1t2.11.1.6` · **Size:** medium
**Created:** 2026-11-16 15:27:13 EST · **Closed:** 2026-11-17 02:56:44 EST
**Plan:** [202611/monitor\_hijack\_adapter.md](https://github.com/sase-org/sase--plans/blob/main/202611/monitor_hijack_adapter.md)

## Description

canary: extend the real fakey launch/loader/TUI-operation canary with a running sleep monitor, same-workspace recovery and command rerun; flip the screenshot-shaped fixture and verify CLI/TUI parity.

## Notes

[2026-11-17T07:15:12Z · sase-1t2.11.1.6--1] PROPOSED FOLLOW-UP: test_session_hijack_chooses_running_member_one flakes in full-file runs (WorkspaceClaimError workspace #3 already claimed at child spawn) but passes solo; seen in 2 consecutive full-file runs of tests/fakey/test_agent_hijack_canary.py, passes in isolation; claim path untouched by this phase (ledger-only Rust change + monitor canary file).

[2026-11-17T07:56:44Z · sase-1t2.11.1.6--2] Monitor hijack recovery canaries green. sase-core ledger: added rerun to HELD_ACTIONS (held-only; expired records still refuse), extended ledger tests; sase-core check passes. Canary assertions corrected (resolution_action field, instruct pinning, follow-up filter by monitor id). This turn fixed the NEW macro-terminology failure the canary introduced (submitted_xprompt string literal now via legacy_xprompt_names constants); macro suite 10 passed, monitor continue+rerun+facts 11 passed. Full sase check b5017e87 otherwise showed only the KNOWN TUI import-budget failure (witness 2051a9b3), unrelated to this work. sase-core fix 35904ebd with pin ratchet is committed (sase HEAD 42f5f6fc); the terminology-constant cleanup in tests/fakey/_agent_hijack_monitor_canary.py is uncommitted in the working tree for host finalizers. Session-hijack member-choice flake remains as PROPOSED FOLLOW-UP on the bead.

## Dependencies

- **Depends on:** [sase-1t2.11.1.4](sase-1t2.11.1.4.md) ✓ · ⧖ 2026-11-16
- **Depends on:** [sase-1t2.11.1.5](sase-1t2.11.1.5.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.7](sase-1t2.11.1.7.md) ✓ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11.1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.1.6.md) | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@35904eb`](https://github.com/sase-org/sase-core/commit/35904ebd0713ea1db7046be1386f9e05c434a52a) | fix(agent-hijack): allow held monitor rerun resolution in ledger | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 2026-11-17 02:27:11 EST |
| sase | [`42f5f6f`](https://github.com/sase-org/sase/commit/42f5f6fc944935ec550d0a420921dcd0eecf5611) | fix(agent-hijack): allow monitor rerun resolution and correct canary assertions | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 2026-11-17 02:28:46 EST |
| sase | [`fa771fe`](https://github.com/sase-org/sase/commit/fa771fe9121c486aca2e160af32c524d30e93619) | fix(agent-hijack): use legacy prompt filename constants in monitor canary | [sase-1t2.11.1.6](sase-1t2.11.1.6.md) | 2026-11-17 02:58:39 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.11.1.6--1][1] | Need full notes and design for failure diagnosis | 2 |
| read-by | [agent:sase-1t2.11.1.6--2][1] | Need bead state before epic-symbols and close | 1 |
| read-by | [agent:sase-1t2.11.1.7][2] | Need predecessor notes, close evidence, and remaining work before land | 1 |
| read-by | [agent:sase-1t2.11.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.1.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.7/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.land/README.md

<!-- sase:referenced-by:end -->

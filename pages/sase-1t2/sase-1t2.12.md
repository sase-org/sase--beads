# Bead: sase-1t2.12 — Doctor check, resolving watchdog, and remote referral tracking

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.12` · **Size:** small
**Created:** 2026-11-15 20:00:12 EST · **Closed:** 2026-11-16 02:55:34 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

ops_polish: a `sase doctor` check for running agents lacking the hijack capability, a watchdog that reconciles resolving records whose successor never dispatches, and local tracking of remote hijack referrals so the mirror row shows the request until the owner host reports an outcome.

## Notes

[2026-11-16T07:09:07Z · sase-1t2.12] PROPOSED FOLLOW-UP: sase-core just check fails on clean master with Clippy needless_bool in grammar.rs, tokenize.rs, and demand.rs — already tracked by sase-1t1

[2026-11-16T07:42:11Z · sase-1t2.12] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py drifts on master (workspace repair argparse vs checked-in cli_spec.json); not caused by ops_polish

[2026-11-16T07:42:24Z · sase-1t2.12] PROPOSED FOLLOW-UP: tests/ace/tui/modals/test_bead_preview_modal.py::test_loading_then_loaded timed out once then passed on rerun (flake)

[2026-11-16T07:55:34Z · sase-1t2.12] ops_polish: doctor agent_hijack.capability; Rust dispatch_timeout watchdog with 300s Python bound; local remote referral store + TUI referred overlay. Verified: targeted hijack/doctor/referral tests; sase-core queued_past_dispatch_bound_returns_to_held; sase tool run check (0b0e27cac4ee6c9aec115b2cd6aba80e). sase-core just check still red on master Clippy needless_bool (sase-1t1).

## Dependencies

- **Blocks:** [sase-1t2.14](sase-1t2.14.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.5](sase-1t2.5.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.6](sase-1t2.6.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.12/README.md) | [sase-1t2.12](sase-1t2.12.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6866f35`](https://github.com/sase-org/sase-core/commit/6866f35bea67fc2609ff1f1ff26c92e6a09b0266) | feat(agent-hijack): return queued resolving records to held after dispatch bound | [sase-1t2.12](sase-1t2.12.md) | 2026-11-16 02:57:17 EST |
| sase | [`3c8564d`](https://github.com/sase-org/sase/commit/3c8564dd8735b014bec17a9f2a8357918dbc5fc6) | feat(agent-hijack): add doctor check, dispatch watchdog, and remote referrals | [sase-1t2.12](sase-1t2.12.md) | 2026-11-16 02:58:57 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t2.12][1] | Need the phase scope, design file, notes, and DECISIONS | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.12/README.md

<!-- sase:referenced-by:end -->

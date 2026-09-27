# Bead: sase-1aq.10.7.5.5 — Audit and land the original remote-dispatch and parity ancestors

[Bead Pages](../README.md) / [sase-1aq.10.7.5](sase-1aq.10.7.5.md) / sase-1aq.10.7.5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.land.md) · **Assignee:** `sase-1aq.10.7.5.5` · **Size:** medium
**Created:** 2026-09-26 21:57:16 EDT · **Closed:** 2026-09-27 00:09:40 EDT
**Plan:** [202609/1aq\_close\_original\_gates.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_close_original_gates.md)

## Description

ancestor_landing: land the sase-xe and sase-133 ancestor chains bottom-up with full land audits, then close sase-1aq.5, .6 and .7 normally.

## Notes

[2026-09-27T04:04:14Z · sase-1aq.10.7.5.5] PROPOSED FOLLOW-UP: follow attention-inventory next_cursor per host in _poll_fleet_attention_inventory — first-page-only fetch leaves >100-row hosts partially mirrored (sase-xe.16.11.7 note #5, sase-168 follow-up 1, mitigation _payload_is_fresh_complete only stops auto-dismiss)

[2026-09-27T04:04:28Z · sase-1aq.10.7.5.5] PROPOSED FOLLOW-UP: cache-only federation reads must carry stale status + last error after a network failure instead of ok/cached:true (sase-xe.16.11.7.14 note #4, sase-168 follow-up 2; honest-freshness scope)

[2026-09-27T04:04:42Z · sase-1aq.10.7.5.5] PROPOSED FOLLOW-UP: tests/core/test_machine_setup_facade.py::test_classify_tailnet_discovery_never_infers_pin fails (incompatible/protocol-unsupported detail) — still red now, reported failing on clean HEAD in sase-xe.16 note #7

[2026-09-27T04:04:56Z · sase-1aq.10.7.5.5] PROPOSED FOLLOW-UP: flake tests/ace/tui/test_machines_pane.py::test_status_check_is_user_triggered_and_records_observation failed once under full-parallel-lane load (KeyError apollo), 3/3 isolated passes; credible _checking_alias/_statuses race in machines_pane.py (sase-xe.16.11.7 note #3)

[2026-09-27T04:09:40Z · sase-1aq.10.7.5.5] ancestor_landing done 2026-09-27: landed bottom-up with full audits — sase-xe.16.11.7.14.6.7, .15, .14.6, .14, .7, .11, .16, sase-xe, sase-133.5, sase-133 — then closed sase-1aq.5/.6/.7 normally, each with requirement-to-evidence note. Verified: no live/WAITING owner on any ancestor (agent list); epic-symbols clean on all 10 ancestors + this phase; tree clean at f83a648ebb, no source changes; link-health suites 13/13 green (disposes .14#3); sase-z6 retired (disposes flag notes); sase-14b tracks golden flake. 4 PROPOSED FOLLOW-UPs recorded here for land-agent triage (attention paging, cache stale status, tailnet facade test red, machines-pane flake). just symvision/check unrunnable (infra timeout rebuilding sase-core-rs, as on .5.2/.5.3). 10 linked plans -> done. Parent epic and sase-1aq left open for .5.6/land agent.

## Dependencies

- **Depends on:** [sase-1aq.10.7.5.3](sase-1aq.10.7.5.3.md) ✓ · ⧖ 2026-09-26
- **Depends on:** [sase-1aq.10.7.5.4](sase-1aq.10.7.5.4.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1aq.10.7.5.6](sase-1aq.10.7.5.6.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.5/README.md) | [sase-1aq.10.7.5.5](sase-1aq.10.7.5.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@8ddd920`](https://github.com/sase-org/sase--plans/commit/8ddd920da7f8ff61cb40c214e9dc46ca9b915218) | chore(plans): mark dispatch and parity epic plans done after ancestor landing | [sase-1aq.10.7.5.5](sase-1aq.10.7.5.5.md) | 2026-09-27 00:11:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1aq.10.7.5.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.5/README.md

<!-- sase:referenced-by:end -->

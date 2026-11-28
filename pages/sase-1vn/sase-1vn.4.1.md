# Bead: sase-1vn.4.1 — Host-owned recovery for zombie epics

[Bead Pages](../README.md) / [sase-1vn.4](sase-1vn.4.md) / sase-1vn.4.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.md) · **Assignee:** `sase-1vn.4.1.land`
**Created:** 2026-11-27 20:17:44 EST
**Plan:** [202611/zombie\_epic\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202611/zombie_epic_liveness.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/zombie_epic_liveness.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/zombie_epic_liveness.md

<!-- sase:links:end -->

## Description

Report stranded completed-child plans and relaunch eligible epic land agents once per new close event.

## Notes

[2026-11-28T07:22:57Z · sase-1vn.4.1.land] LANDING VERIFIED (sase-1vn.4.1 land agent). All 5 phases closed. I checked their commits against the plan: core 91380657 (shared zombie predicate, tree snapshot, close token) and d7416921 (activation/claim records). The sase pin d7416921 is sase-core HEAD and includes both bindings. sase commits: 96e87d5984 (sase bead zombies + TUI badge), 21bdca56ad (machine-owned claim publication, permit only for the published winner), a62aafb718 (deterministic proc id/fingerprint, close-token guard in launch_epic_bead_work, land-only via bead work), a5fde6cd11 (epic_liveness job in the waits routine: 60s, 30s budget, 1 submit/pass, fair cursors, 120s grace, arm-without-launch, docs). Live evidence on sase-1vn.4: file:explicit:95fcc65660f2a5ea7525e495 and file:explicit:2195f969cb91f0108061888d. sase proc list -a -t epic-recovery is empty, so no historical zombie was launched or closed. Drift since the epic started (a6c7603560 plan-work split, bfadafb74b test split) touches nothing the epic added, so no integration was needed. Landing fixes: (1) resolved all 6 sase-1vn.4.1 epic-symbol rows by deleting the test-only submit_recovery_launch_in_store and privatizing the in-file builders (_recovery_proc_id/_request_fingerprint/_concurrency_keys/_claim_request/_proc_request); deleting the in-store entry left publish_recovery_claim_in_store test-only, so it is now private; symvision is clean. (2) epic_liveness counted submission exceptions as deferred because its 'submit_failed' marker never matched; it now uses the REASON_* constants, so they count as failed. (3) A consumed own-host claim with an existing proc row now skips the per-tick publish/push round trip. (4) Added tests the plan required but the job lacked: pre-activation and equal-cutoff closes stay historical, a reclose earns its own token, unknown and non-epic rows never submit, a foreign-owner claim is never transferred, a claim with no proc resumes, a failed submit counts as failed. Shared helpers moved to tests/_epic_liveness_helpers.py. Verified: 58 targeted tests green. sase tool run check abc537ee968537f8f05a7176a3b27344: all lint gates passed; the test lane escalated to 63,960 tests with 1 NEW failure, tests/ace/tui/test_countdown_tick_gc.py (TUI GC, untouched), which passed 3/3 isolated and is filed as flake sase-1vx. FOLLOW-UP TRIAGE: 4.1.1 note #1 (sase-core query_cache timing) became new task sase-1vv. 4.1.2 note #1 (admission test_limit_two overlap flake) became new task sase-1vw, linked related to sase-1ve (a different node in the same module). 4.1.3 note #1 (refresh_warmup_gc) was declined as a new task: sase-1v2 already owns it through its KNOWN triage signature (witness 207e3123), so no +1 was added.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.4.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.land/README.md) | [sase-1vn.4.1](sase-1vn.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8610438`](https://github.com/sase-org/sase/commit/8610438838bd9fe2425be487cb5b2c56bdc72172) | fix(axe): land zombie-epic recovery and harden epic\_liveness accounting | [sase-1vn.4.1](sase-1vn.4.1.md) | 2026-11-28 02:24:54 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vn.4.1.3][1] | Need child epic phase IDs for epic-symbol re-keying | 2 |
| read-by | [agent:sase-1vn.4.1.5][2] | Need governing decisions and parent context for this assigned phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.5/README.md

<!-- sase:referenced-by:end -->

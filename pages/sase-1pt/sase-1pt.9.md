# Bead: sase-1pt.9 — Finish the durable-publication-enqueue landing (publisher repairs and an installed re-prove)

[Bead Pages](../README.md) / [sase-1pt](README.md) / sase-1pt.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pt.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pt.land.md) · **Assignee:** `sase-1pt.9.land`
**Created:** 2026-10-30 03:24:16 EDT · **Closed:** 2026-11-02 16:57:53 EST
**Plan:** [202610/commit\_publication\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/commit_publication_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/commit_publication_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:87ff881a17a8bfdab19da4bd | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/commit_publication_landing_repairs.md

<!-- sase:links:end -->

## Description

The background publisher from epic sase-1pt idles when it has no work. It converts the fenced Referenced By backlog itself and never holds a hood acknowledgment hostage to an unrelated drain. The epic's latency and sidecar reliability claims are then measured on an athena install that actually contains the epic.

## Notes

[2026-11-02T21:19:41Z · sase-1pt.9.land] LANDING VERIFICATION + FOLLOW-UP TRIAGE (sase-1pt.9.land, master 84e22d98be). Verified: publisher-repairs (sase-1pt.9.1, 6d615680b8) items 1-3 are on master unchanged in intent (completed link drains release hints and report retained rows; fenced Referenced By backlog converts in the publisher; deferred acknowledgment runs only per-request side effects while the synchronous path still drains). Later commits touching these files (sase-1qh.1/.2/.4/.6, sase-1pj.6.1/.6.1.8, docs refreshes) neither conflict with nor duplicate them. Its 29 regression tests pass on master. REMAINING EPIC WORK: (a) item 4 missed deleting the stale Justfile comment 'sase-1pt.6 provides publisher_is_live for the enqueue-only caller in sase-1pt.7.'; (b) sase-1pt.9.2 was closed by a human after collection only. Its checkpoint (file:explicit:7016ae2d8528704b800b8bff) lists measure, audit, and report as remaining, and no report artifact exists. The collector holds 73 qualifying runs (2 booted-before-install and 4 conflict-repair exclusions), stopped 2026-11-01T11:22Z. Planned as a lander-authored tale that also performs this closeout. FOLLOW-UP TRIAGE: (1) sase-1pt.9.1 #1 completion snapshot drift + agent/sync kind-coverage -> DECLINED, already fixed: tests/completion/test_snapshot.py (4) and tests/completion/test_kind_coverage.py (7) pass on 84e22d98be. (2) sase-1pt.9.1 #3 stale Justfile --epic-symbol rows for sase-1pj.5.1.2 and sase-1pj.4.1.6 -> DECLINED, already fixed: no such rows remain; the sase-1pj.4.1 landing dropped them. sase-1pt.9.2 recorded no PROPOSED FOLLOW-UP entries.

[2026-11-02T21:37:36Z · sase-1pt.9.land] RE-PROVE TRIAGE (finish_publication_reprove_landing, 73-run installed sample 2026-10-30T13:06Z to 2026-11-01T11:22Z, host 207ded297a contains 6d615680b8): (1) LATENCY residual — provider_done->done med 101.3s/p95 200.6s vs baseline med 346.5s/p95 562.1s (~3.4x better) but median +41.3s and finalizer p95 ~178-201s still miss <60s targets; causes bead_pages ~38s med + just-fix ~21s med, hood enqueue only 0.6s; queue-age p95 547s <600s passes, background branch 73/73, idle 86% -> filed task sase-1qx (bug, large), no epic fix (no busy-loop, no inline fallback while live). (2) HOOD gaps 2/73 (research.5l.image/linker, linked scope, 120s drain-timeout quarantined; commits fine) -> routed to active epic sase-1qh as DISCOVERED ISSUE (sase-1qh.7 owns stuck research rows), no new task. (3) CITES/REFBY residual — 77 refby rows byte-identical to install (never converted; protection-gated, SDD dirty-clone errors) + 1 pending cites event (16n/20261031114701, release row also present, ambiguous) -> filed task sase-1qy (bug, medium). (4) PIN-ONLY conflicts: none in window (4 excluded repairs all multi-file), resolver unexercised, no misfire. (5) RETENTION healthy (hourly enforced, 0 trashed); sase-1nf.11 3531->3545 quarantined hood rows still confound queue ages (noted, owned there). No unresolved epic-caused blocker: closeout proceeds.

[2026-11-02T21:51:49Z · sase-1pt.9.land] REPORT (finish_publication_reprove_landing): installed re-prove measured and audited. Sample: 73 qualifying no-conflict runs, 2026-10-30T13:06Z install (host 207ded297a contains 6d615680b8) to 2026-11-01T11:22Z truncation (46.3h; >=30 minimum, <100 target); 6 exclusions (2 booted-before-install, 4 multi-file conflict repairs, 0 pin-only). Headline numbers: provider_done->done med 101.3s/p95 200.6s (baseline 346.5/562.1); finalizer p95 ~178-201s (baseline 802.9); publication med 38.9s (baseline 255.4, bead_pages 38.2s dominates); queue-age p95 547s <600s PASS; background branch 100% (73/73), 0 inline; drains 109 published/30 idle/18 lock_busy/6 failed/19 timeout. Audit: 73/73 pushed+published, hood acked 71/73 (2 linked-scope research rows quarantined on 120s drain timeout -> sase-1qh note), prompt archives 73/73, hood pages 73/73, link drained 72/73 (1 pending cites -> sase-1qy), refby 77 unchanged (protection-gated -> sase-1qy). Residuals filed: sase-1qx (latency, large, ready), sase-1qy (refby+cites, medium, ready). Full report: file:explicit:87ff881a17a8bfdab19da4bd. Justfile stale comment removed. No epic-caused blocker.

[2026-11-02T21:57:53Z · sase-1pt.9.land] finish_publication_reprove_landing tale complete: publisher-repairs on master and tested (29 regression tests, verified at 84e22d98be); installed re-prove measured and audited (report file:explicit:87ff881a17a8bfdab19da4bd, n=73, 71/73 hood-acked with 2 linked-scope rows routed to sase-1qh, residuals filed as sase-1qx/sase-1qy ready); Justfile stale sase-1pt.6 comment removed (only change; just fix clean; sase tool run check run 61e27425 all lint gates green incl. symvision, test lane joined to monitor). No epic-caused blocker.

[2026-11-02T22:02:24Z · sase-1pt.9.land] TESTED (finish_publication_reprove_landing): sase tool run check 61e27425f50e277e59c935d797d3243a SUCCEEDED (exit 0, 19m49s) — all lint gates plus the diff-scoped test lane green on the tree with the Justfile comment removal. The earlier escalation (8m30s ceiling) and monitor-join attempt were overtaken: the run settled green on its own. No pre-existing failure to document.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pt.9.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pt.9.land.md) | [sase-1pt.9](sase-1pt.9.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce7d60a`](https://github.com/sase-org/sase/commit/ce7d60a6666401567a0071945070c6f8c844031e) | chore(justfile): drop stale sase-1pt.6 publisher\_is\_live comment | [sase-1pt.9](sase-1pt.9.md) | 2026-11-02 17:04:13 EST |
| sase--plans | [`sase--plans@f4d6404`](https://github.com/sase-org/sase--plans/commit/f4d6404d90555b7b8c96783d9facc10475fcc442) | chore(plans): mark sase-1pt.9 and sase-1pt epic plans done | [sase-1pt.9](sase-1pt.9.md) | 2026-11-02 17:05:40 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pt.9.1][1] | Need parent epic decisions and phase context before implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.9.1/README.md

<!-- sase:referenced-by:end -->

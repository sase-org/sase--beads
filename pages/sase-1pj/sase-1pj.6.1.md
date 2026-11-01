# Bead: sase-1pj.6.1 — Recover staged handoffs without repeating adoption

[Bead Pages](../README.md) / [sase-1pj.6](sase-1pj.6.md) / sase-1pj.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.md) · **Assignee:** `sase-1pj.6.1.land`
**Created:** 2026-10-31 08:56:53 EDT · **Closed:** 2026-11-01 14:29:29 EST
**Plan:** [202610/staged\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/staged_handoff_recovery.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 9 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/staged_handoff_recovery.md

<!-- sase:links:end -->

## Description

Make every staged handoff replayable after runner death, reconcile completed turns, and let held handoffs be explicitly re-adopted after their obligations are satisfied.

## Notes

[2026-11-01T15:28:47Z · 16p--code] DISCOVERED ISSUE: Monitor settlement after a live sase update crashes on stale in-process code and drops the follow-up. Evidence from athena 2026-11-01 restart triage: 4 monitors SIGTERM'd (sase-1oe.4--mon-3 g3we4m00jd30, sase-1q2.9.2--mon 6arwy6wqewnh, sase-1pt.9.2--mon 5zwebkfet1r3, sase-1n6.10--mon hdywq4jz9fjt) each stopped exit -15 with settlement errors: release_workspace() unexpected artifacts_timestamp, and sase_core_rs missing binding decide_workspace_retention (x3). Install is editable, primary checkout updated 07:08, supervisors started before that. Follow-ups never launched. Causally belongs to staged-handoff recovery / workspace retention.

[2026-11-01T15:29:47Z · 16p--code] DISCOVERED ISSUE: sase-core master CI red on rustfmt-only since 73ec04a02a (run 41225348868) on crates/sase_core/src/staged_handoff/mod.rs and recovery.rs, blocking daily core cut and release chain (sase-1q2.9.2, sase-1oe.4, sase-1pi.1 via sase-1n6.10). Per core_fmt=fix, this recovery lands the formatting-only fix; no bead tracks the failure, sase-1oe.4 names sase-1pj.6.1 as owner.

[2026-11-01T15:45:03Z · sase-1pu.5.1.5.1] DISCOVERED ISSUE: Independent phase verification ran ToolRun f67af1ce29377847573102c786729866 (`sase tool run check`) at the clean base HEAD 764317b9 and exited 1 only on rustfmt differences in four unchanged staged_handoff files: core mod.rs, recovery.rs, tests.rs, and Python mod.rs. These files were clean at phase start and are outside the published-state changes. This independently confirms existing note #2 and its assignment to this recovery epic; no separate task bead is needed.

[2026-11-01T17:50:39Z · sase-1pu.5.1.5.land] LAND FOLLOW-UP RESOLVED: Rechecked phase sase-1pu.5.1.5.1 note 1 and this epic notes 2-3. The four staged_handoff rustfmt changes are now committed in linked sase-core dc119c0b by closed phase sase-1qk.1; its recorded fmt-check passed. Declined a new task or further corroboration because the proposed formatting repair has landed. The core run-state pin dc5383f6 already contains the required bindings; this formatting-only follow-up does not require changing that feature pin.

[2026-11-01T18:32:38Z · sase-1pj.6.1.land] LAND FOLLOW-UP TRIAGE (sase-1pj.6.1.land): sase-1pj.6.1.2 #1 (TUI import budget 2863 vs cap 2861) and sase-1pj.6.1.5 #1 (the same node failing on the clean base under load) are semantic duplicates of open sase-1ic. Corroborated them with one +1 (now +35). sase-1pj.6.1.2 #2 (create-project review button sees 'checking' under xdist) had no owner, so I created flake task sase-1ql (ready). sase-1pj.6.1.5 #2 (split start_stage_adopt.py) is declined: 877fef9203 already split it into a 33-line facade plus _start_stage_adopt_* modules. sase-1pj.6.1.8 #3 (stale_worktree_fingerprint refusal of an unchanged prepared completion) had no owner, and its code predates every active epic, so I created bug task sase-1qm (ready). Epic note #1 (monitor settlement crashes on stale in-process code after a live update) is not caused by this epic: release_workspace(artifacts_timestamp=) and decide_workspace_retention come from sase-1pj.7.1.1 and are reached through 7.1.2. I recorded it as a DISCOVERED ISSUE on active epic sase-1pj.7.1. Epic notes #2-#4 (core rustfmt) are declined as resolved: sase-core dc119c0b landed the format fix, and pin 16a3ed0f contains it. The integration seam (stale-cleanup staged-origin retention overrides the held-claim TTL, and recovery-service holds write no retention record) is recorded as a DISCOVERED ISSUE on sase-1pj.7.1 for its in-progress recovery-surfaces phase 7.1.4, which owns TTL and surfacing policy. Remaining epic-caused work goes to a lander tale: detached successor delivery must take over the dead origin's workspace claim, and recovery-discovered holds must send one deduplicated readopt notification.

[2026-11-01T19:29:29Z · sase-1pj.6.1.land--1] Verification: all eight phases are closed and landed — 6.1.1 d3d26a5b55, 6.1.2 b674079c2b, 6.1.3 9c17b8454b, 6.1.4 d9129cfd4b, 6.1.5 6a2c90f41b, 6.1.6 406c57f126, 6.1.7 288d2afeeb, and 6.1.8 a19243cdf6. Core recovery commits 73ec04a0 and 16a3ed0f are both in the sase-core-revision.txt pin; the pin names 16a3ed0f, whose history descends from 73ec04a0. The recovery work integrates with workspace-retention phases sase-1pj.7.1.1–7.1.3 and lost-gate withdrawal phase sase-1qk.4, with the staged recovery/adoption/delivery refactor splits preserved. Epic follow-up triage note #5 was reviewed: duplicate TUI import-budget failures were corroborated on sase-1ic; create-project flake sase-1ql and stale-worktree bug sase-1qm were filed; the already-landed start-stage split and resolved core rustfmt follow-ups were declined; monitor-settlement and retention integration follow-ups were routed to sase-1pj.7.1; this tale owns the remaining two gaps. This tale transfers a dead origin workspace claim atomically in both detached spawn paths, holds conflicts for retry, and tests pinned claims; it also sends recovery-discovered hold notices with origin/stage/reason deduplication while reusing the runner wording. The focused matrix including tests/test_staged_successor_claim_handover.py passed 150 tests. ToolRun ca821370d66d97873b1185d31ed48488 ran check: lint, docs, and Symvision passed; scoped tests had 29 unrelated failures (26 NEW and 1 FLAKY triage items), matching the documented parallel-lane failures in sase-1qk.4 note #1; six representative failures passed serially. Standalone just symvision passed cleanly.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.land.md) | [sase-1pj.6.1](sase-1pj.6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`078e3da`](https://github.com/sase-org/sase/commit/078e3da1d6a784cfc8fd2ab783273246318660c2) | fix(axe): recover staged successor claim handovers | [sase-1pj.6.1](sase-1pj.6.1.md) | 2026-11-01 14:34:16 EST |
| sase--plans | [`sase--plans@bc18a97`](https://github.com/sase-org/sase--plans/commit/bc18a97ac672906d8b2ad6222c9bd669a73a5ea2) | docs(plan): close staged handoff recovery phase | [sase-1pj.6.1](sase-1pj.6.1.md) | 2026-11-01 14:36:02 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.6.1.1--2][1] | Need epic decisions and plan | 1 |
| read-by | [agent:sase-1pj.6.1.2][2] | Need binding epic decisions and phase notes before implementation | 1 |
| read-by | [agent:sase-1pj.6.1.3][3] | Need epic decisions and phase design context | 1 |
| read-by | [agent:sase-1pj.6.1.4][4] | Need parent epic DECISIONS and remaining phases | 1 |
| read-by | [agent:sase-1pj.6.1.5][5] | need decisions | 1 |
| read-by | [agent:sase-1pj.6.1.6--1][6] | Need epic DECISIONS | 2 |
| read-by | [agent:sase-1pj.6.1.7][7] | Need epic decisions governing this phase | 1 |
| read-by | [agent:sase-1pj.6.1.land--1][8] | Need epic notes and land triage before finishing the approved staged-recovery tale | 2 |
| read-by | [agent:sase-1pu.5.1.5.1][9] | Need the active staged-handoff epic note that owns the unchanged-file rustfmt failure | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.4/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.5/README.md
[6]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.6.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.6.1.7/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.6.1.land.md
[9]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.1/README.md

<!-- sase:referenced-by:end -->

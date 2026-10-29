# Bead: sase-1pn.3 — Make the epic close guard see upstream --epic-symbol rows (sase-o7)

[Bead Pages](../README.md) / [sase-1pn](README.md) / sase-1pn.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pm.land.md) · **Size:** medium
**Created:** 2026-10-29 10:44:08 EDT · **Closed:** 2026-10-29 12:25:13 EDT
**Plan:** [202610/task\_backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_2.md)

## Description

close-guard: have sase bead close and sase bead epic-symbols read the fetched default branch's Justfile as well as the local one, so sibling-phase whitelist rows cannot escape the close.

## Notes

[2026-10-29T16:09:03Z · sase-1pn.3] Status: implementation complete, verification running. close-guard change (upstream Justfile union + update --status closed guard) is in the working tree; `sase bead epic-symbols sase-1pn.3` and `sase-1pn` both report no leftovers. `sase tool run check` run 15740c604fa23ba51d679d4c7b5472cb is in the test lane (all lint gates incl. symvision green); handed to a verify monitor for the final verdict.

[2026-10-29T16:24:48Z · sase-1pn.3--1] PROPOSED FOLLOW-UP: stale contract manifest on clean base — test_contract_manifest_matches_marker_selection fails identically on HEAD cddea47cc6 (marker selects test_core_finalizer_handoff.py and test_ratchet_core_window_tool_ref.py, both already marked contract on base); tracked by sase-1pg/sase-1pi/sase-1pj.2.1 per sase-1pn.1 note

[2026-10-29T16:24:55Z · sase-1pn.3--1] PROPOSED FOLLOW-UP: load-flaky scoped NEW items pass in isolation — test_agy_usage_probe timeout-vs-rate_limited, test_reload_allows_missing_target_to_resolve, and test_multiple_groups_expand_primary all pass on clean base and on this worktree in isolation (6s) but failed under full-check load (74s call, WaitForScreenTimeout); not touched by this bead diff

[2026-10-29T16:25:13Z · sase-1pn.3--1] TASK RESOLVED: sase-o7 — close guard unions default-branch Justfile epic-symbol rows with local ones (bounded fetch, stale-ref fallback, never wedges); epic-symbols clean for sase-1pn.3 and sase-1pn. Focused bead tests 26 passed. Full check run 15740c604fa23ba51d679d4c7b5472cb: lint green, scoped 58775 passed; 4 NEW proven unrelated (contract-manifest reproduces on clean base cddea47cc6; other 3 pass in isolation on both trees) plus 2 KNOWN 2 FLAKY. No commit per host-owned completion; 8-file change in worktree for land.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pn.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.3.md) | [sase-1pn.3](sase-1pn.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pn.3--1][1] | Verify phase closed | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.3.md

<!-- sase:referenced-by:end -->

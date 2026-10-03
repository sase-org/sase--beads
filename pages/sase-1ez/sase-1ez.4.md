# Bead: sase-1ez.4 — Take automatic gen-2 collection off the interactive path

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.4` · **Size:** medium
**Created:** 2026-10-02 16:45:01 EDT · **Closed:** 2026-10-02 21:45:03 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

idle-gc-policy: once startup loads settle and input first goes idle, run gc.collect() then gc.freeze() exactly once. Raise threshold2 to 10_000 on the classic three-generation collector. Run tagged full collections only when input has been quiet for 3 s, no prompt is active, and a collection is due, with 5-minute and RSS-growth backstops and an off-thread malloc_trim. Includes an env kill switch, a clean uninstall, and no install under the testing harness.

## Notes

[2026-10-03T01:44:41Z · sase-1ez.4--1] PROPOSED FOLLOW-UP: just check full-suite escalation shows 2 KNOWN failures unrelated to idle-gc-policy (test_prompt_key_io_probe_counts_main_thread_calls witness 4bd69d8aca0427947e28d2f228156ead; test_busy_cluster_compacts_narrow_and_restores_wide witness 9d2cc9514de3b284d26268fc5af548c8); verdict no_new_failures

[2026-10-03T01:45:03Z · sase-1ez.4--1] idle-gc-policy implemented (gc_policy.py + wiring + harness guard + docs); phase tests 21 passed; just check escalated to full suite: 51810 passed with 2 KNOWN failures (witnesses 4bd69d8a, 9d2cc951), verdict no_new_failures; epic-symbols clean

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.3](sase-1ez.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ez.8](sase-1ez.8.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.4.md) | [sase-1ez.4](sase-1ez.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f7d2c2c`](https://github.com/sase-org/sase/commit/f7d2c2c09e51c43002d1827d2950290dc7ca9916) | feat(tui): take automatic gen-2 collection off the interactive path (sase-1ez.4) | [sase-1ez.4](sase-1ez.4.md) | 2026-10-02 21:53:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ez.4--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ez.4.md

<!-- sase:referenced-by:end -->

# Bead: sase-1ev.10 — Memory as seen by the agent in the Agents tab

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.10` · **Size:** medium
**Created:** 2026-10-02 14:43:18 EDT · **Closed:** 2026-10-02 20:43:58 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

agents-bridge: add a sase-core blob:OID version selector. The Agents-tab MEMORY lane gets version chips per read (aggregate for batch reads) and an AGENTS.md as launched row resolved from launch evidence, including a not-in-git snapshot pseudo-version. Hints open the pager pinned to the version read.

## Notes

[2026-10-03T00:43:38Z · sase-1ev.10--2] Repaired 7 deterministic header-enrichment regressions from agents-bridge (enrich_memory_versions copied the summary breaking `is` identity; extra post-loop partial publish broke exact publish counts). Fix: enrich runs on the memory batch before its own publish, returns summary unchanged when nothing resolves. Full just check (22-31m) exceeds single-turn limits; verified via targeted suites instead.

[2026-10-03T00:43:58Z · sase-1ev.10--2] Verified: 14 header-enrichment tests pass; bead suites (110) + widgets (6187) + actions/memory (878) + visual snapshots (2) pass; symvision clean; no epic-symbol leftovers. force_reuse/demand failures seen only under full-suite parallel load, pass in targeted runs on this tree (unrelated code paths).

[2026-10-03T01:51:27Z · sase-1ev.10--3] PROPOSED FOLLOW-UP: just-check full suite shows 2 failures unrelated to sase-1ev.10 — test_prompt_key_io_probe_counts_main_thread_calls fails identically on clean base (stale vcs_xprompt_mru.json expectation vs canonical vcs_macro_mru.json), test_foreground_run_records_context_usage_and_grant passes in isolation on both trees (parallel-load flake on peak_tree_rss_kib)

## Dependencies

- **Blocks:** [sase-1ev.11](sase-1ev.11.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ev.2](sase-1ev.2.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.10.md) | [sase-1ev.10](sase-1ev.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ba63f9d`](https://github.com/sase-org/sase-core/commit/ba63f9dfd99916765c989fcd380313591c936728) | feat(core): add memory history query and cache coverage | [sase-1ev.10](sase-1ev.10.md) | 2026-10-02 20:46:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.10--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ev.10.md

<!-- sase:referenced-by:end -->

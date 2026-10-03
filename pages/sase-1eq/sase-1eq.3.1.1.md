# Bead: sase-1eq.3.1.1 — Query-language shorthands

[Bead Pages](../README.md) / [sase-1eq.3.1](sase-1eq.3.1.md) / sase-1eq.3.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.md) · **Assignee:** `sase-1eq.3.1.1` · **Size:** medium
**Created:** 2026-10-02 19:30:25 EDT · **Closed:** 2026-10-02 20:57:44 EDT
**Plan:** [202610/sase\_modules\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md)

## Description

shorthands: Rename the query-language status-macro concept to shorthand, including the profile wire key sent to core, before any xprompt rename.

## Notes

[2026-10-03T00:57:14Z · sase-1eq.3.1.1--1] PROPOSED FOLLOW-UP: tests/ace/tui/test_prompt_key_perf_smoke.py::test_prompt_key_io_probe_counts_main_thread_calls fails identically on clean base tree (FileNotFoundError vcs_xprompt_mru.json) — pre-existing, unrelated to shorthands rename

[2026-10-03T00:57:26Z · sase-1eq.3.1.1--1] PROPOSED FOLLOW-UP: tests/ace/tui/test_top_bar_indicators.py::test_busy_cluster_compacts_narrow_and_restores_wide is flaky (failed in check fdb7f67748d8342882a37eab46b743f7, passed on isolated rerun with rename applied) — pre-existing, unrelated to shorthands rename

[2026-10-03T00:57:44Z · sase-1eq.3.1.1--1] Shorthands rename done: 30 files under src/sase/ace and tests. Verified: fmt+model-policy gates pass, rename lane 156 passed (query_profile compile/compat/agents/beads/files/patches/plans/procs/provider/stitches, profile_highlighting, patch_filter_bar), wire round-trip through compile_query_with_profile covered. Full check fdb7f67748d8342882a37eab46b743f7 had 2 scoped failures both pre-existing (prompt_key_io_probe fails identically on clean base; top_bar busy_cluster flaky, passes on rerun). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1eq.3.1.2](sase-1eq.3.1.2.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.3.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.1.1.md) | [sase-1eq.3.1.1](sase-1eq.3.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d9d0cae`](https://github.com/sase-org/sase/commit/d9d0cae9f0dc7b9f96270e189fd80861d61e7771) | refactor(ace): rename query-language status-macro concept to shorthand (sase-1eq.3.1.1) | [sase-1eq.3.1.1](sase-1eq.3.1.1.md) | 2026-10-02 20:59:08 EDT |

# Bead: sase-1lh.3 — Stop one-off capture drift from failing the visual lane

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.3` · **Size:** medium
**Created:** 2026-10-16 13:00:20 EDT · **Closed:** 2026-10-16 14:25:31 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

visual-stability: apply the accepted visual_flakes policy so a capture race no longer reds Full CI by itself.

## Notes

[2026-10-16T18:25:17Z · sase-1lh.3] PROPOSED FOLLOW-UP: sase tool run check (ba2799f197dadd82605f4c5078f1f35b) test-scoped reported 5 NEW + 2 KNOWN failures unrelated to recapture: test_sdd_canonical_layout flags docs/contribute/perf-runbook.md (exclude is perf_runbook.md); test_macro_docs_and_memory_avoid_xprompt_terms hits docs/macros.md and docs/_meta; test_plugins_required_gate_preview missing "one combined install"; TUI next-word peek and tool-run reconnect timeouts; KNOWN monitor reparent + beads plus-one close docs. Recapture tests passed inside 56107-pass scoped run.

[2026-10-16T18:25:31Z · sase-1lh.3] Check-mode recapture: just fix-tui-screenshots --check re-runs <=25 first-pass failures serially (workers=1, up to 2 verify attempts), passes only exact golden matches, reports retry-only nodes as unstable, writes first-attempt diffs, and exits 1 on remaining drift. CI locates the report always(), publishes an Unstable GITHUB_STEP_SUMMARY table on green, and uploads first-attempt-diffs. Tests cover first-pass pass, retry unstable, fail-all, over-cap; lint_and_test.md --check sentence and development.md updated. Verified: recapture pytest file + related screenshot tests, just fix, sase tool run check (fmt/lint/docs green; scoped 56107 passed including recapture tests; 5 NEW+2 KNOWN unrelated failures noted as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.3/README.md) | [sase-1lh.3](sase-1lh.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae7f9dc`](https://github.com/sase-org/sase/commit/ae7f9dc91aa7504022d17e5b8c9343d912271a13) | feat(visual): recapture first-pass screenshot check failures | [sase-1lh.3](sase-1lh.3.md) | 2026-10-16 15:19:09 EDT |

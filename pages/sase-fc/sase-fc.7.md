# Bead: sase-fc.7 — Cross-surface audit and documentation

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.7` · **Size:** small
**Created:** 2026-08-05 16:29:10 EDT · **Closed:** 2026-08-05 19:00:09 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

audit: sweep the repo for any remaining bead-rendering site that omits creation time, add a regression test that enumerates the covered surfaces, document the created-time contract in docs/beads.md, and run just check.

## Notes

[2026-08-05T22:59:45Z · sase-fc.7] PROPOSED FOLLOW-UP: symvision flags progress_fingerprint in src/sase/llm_provider/commit_finalizer_git.py as an unused public function (from commit 840cdff10), but it is actually called via finalizer_git.progress_fingerprint(...) attribute access in commit_finalizer.py — symvision does not track that call form. Pre-existing on master, unrelated to sase-fc; fix by making the symvision scan aware of attribute-call usage or by adding a documented exception.

[2026-08-05T22:59:53Z · sase-fc.7] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_artifacts_beads.py::test_artifacts_beads_populated_png_snapshot fails on master (pre-existing, reproduced on a clean checkout with no sase-fc.7 changes applied) with a 2.96% pixel mismatch against tests/ace/tui/visual/snapshots/png/artifacts_beads_populated_120x40.png. Needs investigation/regeneration of the golden — unrelated to the sase-fc cross-surface creation-time audit.

[2026-08-05T23:00:09Z · sase-fc.7] Swept the repo for bead-rendering sites missing creation time; only src/sase/bead_pages/roster.py's root roster table lacked a Created column, now fixed via bead_date_label. Added tests/test_bead_time_surface_coverage.py enumerating 18 covered surfaces plus documented exceptions (dep-edge timestamp, artifact-ref completion age column, Mermaid graph). Documented the created-time contract (glyphs, density tiers, live-vs-persisted rule, exceptions) in a new docs/beads.md#creation-time-presentation section. Updated two roster-dependent tests for the new column. Verified: pytest on the new coverage file plus both modified roster tests (41 passed); just lint passes except one pre-existing, unrelated symvision false-positive from commit 840cdff10 (progress_fingerprint flagged unused despite being called via attribute access — confirmed pre-existing and reproduced identically on a clean stash of master); just test (25940 passed, 7 skipped) except one pre-existing visual snapshot failure (test_artifacts_beads_populated_png_snapshot) reproduced identically with my changes stashed out, confirming it predates this work. Both pre-existing failures recorded as PROPOSED FOLLOW-UP notes on this bead.

## Dependencies

- **Depends on:** [sase-fc.1](sase-fc.1.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fc.2](sase-fc.2.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fc.3](sase-fc.3.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fc.4](sase-fc.4.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fc.5](sase-fc.5.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fc.6](sase-fc.6.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.7/README.md) | [sase-fc.7](sase-fc.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4330fd0`](https://github.com/sase-org/sase/commit/4330fd0d5a6f2e36a84e8142d902faaf282a37c0) | feat(bead): add roster creation-time column and regression coverage | [sase-fc.7](sase-fc.7.md) | 2026-08-05 19:00:42 EDT |

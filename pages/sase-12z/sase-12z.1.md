# Bead: sase-12z.1 — Collect complete screenshot candidates without changing goldens

[Bead Pages](../README.md) / [sase-12z](README.md) / sase-12z.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mx.md) · **Assignee:** `sase-12z.1` · **Size:** medium
**Created:** 2026-09-18 10:39:51 EDT · **Closed:** 2026-09-18 11:43:17 EDT
**Plan:** [202609/fix\_tui\_screenshots.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots.md)

## Description

capture-protocol: add an isolated, versioned candidate-capture protocol to the shared ACE and pager fixtures, with xdist-safe records, execution completeness evidence, and focused regression tests. Preserve existing rendering, convergence checks, and direct comparison behavior.

## Notes

[2026-09-18T15:42:41Z · sase-12z.1] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py failed in the escalated full suite with CLI completion-spec drift (argparse-tree snapshot key order) — unrelated to capture-protocol; regenerate or investigate the checked-in completion spec

[2026-09-18T15:43:17Z · sase-12z.1] Added an isolated, versioned candidate-capture protocol for ACE and pager PNG fixtures. Capture sessions write worker-local PNG/SVG/metadata under --sase-visual-capture-dir without comparing or updating goldens, merge deterministically on the controller, and record execution completeness (full vs targeted, worker loss, skips/xfails/failures, duplicate canonical paths, path escapes). Direct assert_png_matches and temp-root helper tests stay on the old compare/update path. Verified: 25 focused capture tests (including a real -n 2 xdist fixture project and golden-tree hashes unchanged), 28 existing png_diff tests, ruff/mypy/symvision, and an escalated full non-visual suite (42975 passed; 2 completion-spec snapshot failures are unrelated).

## Dependencies

- **Blocks:** [sase-12z.2](sase-12z.2.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12z.1/README.md) | [sase-12z.1](sase-12z.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da4caa9`](https://github.com/sase-org/sase/commit/da4caa94cff22a9319c76f82f9fd440ec52523d7) | test(visual): add isolated screenshot candidate-capture protocol | [sase-12z.1](sase-12z.1.md) | 2026-09-18 11:44:59 EDT |

# Bead: sase-qd.5 — Documentation and visual proof

[Bead Pages](../README.md) / [sase-qd](README.md) / sase-qd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.5` · **Size:** small
**Created:** 2026-08-18 18:14:40 EDT · **Closed:** 2026-08-18 20:30:24 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

docs-visual: rewrite the "Current project" and "Projects Tab" sections of docs/ace.md, document the new keymap scope in docs/configuration.md, add a PNG golden that shows the current-project row and detail block, and run the full verification lane.

## Notes

[2026-08-19T00:30:03Z · sase-qd.5] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_axe_layout.py::test_axe_constrained_width_no_wrap_png_snapshot flakes under the full `just test-visual` xdist parallel run (3.9% changed pixels vs golden) but passes cleanly in isolation (`pytest -p no:xdist -m visual`). Unrelated to this phase's diff (docs + config-center-projects visual tests) — file a flake bead once reproduced again.

[2026-08-19T00:30:24Z · sase-qd.5] Rewrote ace.md Current project + Projects Tab sections (CUR marker, c key, accent name, summary segment, +CURRENT badge, detail line) and documented ace.keymaps.projects + tightened current_project.indicator in configuration.md; prettier-formatted. Added _patch_project_records current_project stub plumbing and a new PNG golden (config_center_projects_current_120x40) exercising the current-project row/badge, generated via --sase-update-visual-snapshots. No --epic-symbol entries. just install + just test-visual (-k config_center_projects_current, passed) + full just test-visual (720 passed, 1 unrelated pre-existing flake in axe_layout confirmed to pass in isolation, noted as follow-up) + just check (all lint gates + scoped tests) all green.

## Dependencies

- **Depends on:** [sase-qd.4](sase-qd.4.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.5/README.md) | [sase-qd.5](sase-qd.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`60bc311`](https://github.com/sase-org/sase/commit/60bc311503c9e32fc121d943da6fe336bd7ae971) | docs(ace): document current-project display and add its visual golden | [sase-qd.5](sase-qd.5.md) | 2026-08-18 20:31:08 EDT |

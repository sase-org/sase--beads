# Bead: sase-mf.3 — Redesign Models around launch settings and flat size aliases

[Bead Pages](../README.md) / [sase-mf](README.md) / sase-mf.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02n.md) · **Assignee:** `sase-mf.3` · **Size:** medium
**Created:** 2026-08-15 14:30:43 EDT · **Closed:** 2026-08-15 17:53:39 EDT
**Plan:** [202608/simplify\_models.md](https://github.com/sase-org/sase--plans/blob/main/202608/simplify_models.md)

## Description

models_panel_redesign: build a unified navigable panel for model settings, effort, runner limit, five built-ins, and responsive user-owned aliases and buckets.

## Notes

[2026-08-15T21:52:57Z · sase-mf.3] PROPOSED FOLLOW-UP: Unrelated bead-work changes in the current checkout fail ruff formatting and Symvision, blocking a clean rerun of just check outside the Models-panel scope.

[2026-08-15T21:53:39Z · sase-mf.3] Verified targeted ruff format/check on Models-panel files, .venv/bin/pytest tests/test_models_panel_*.py (248 passed), and just test-visual -- tests/ace/tui/visual/test_ace_png_snapshots_models_panel*.py (39 passed). Attempted just check: lint stages passed and full-suite scoped lane reached 30511 passed/10 skipped before interruption; rerun blocked by unrelated bead-work formatting/Symvision changes noted as follow-up.

## Dependencies

- **Depends on:** [sase-mf.2](sase-mf.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mf.4](sase-mf.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.3/README.md) | [sase-mf.3](sase-mf.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`28da68d`](https://github.com/sase-org/sase/commit/28da68d4e325d38587c9703a5db683ee8a13af76) | feat(tui): redesign Models panel around launch settings | [sase-mf.3](sase-mf.3.md) | 2026-08-15 17:57:07 EDT |

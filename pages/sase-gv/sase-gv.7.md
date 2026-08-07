# Bead: sase-gv.7 — Statistics tab jump to numbered views

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.7` · **Size:** small
**Created:** 2026-08-07 09:53:24 EDT · **Closed:** 2026-08-07 11:10:21 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

statistics: make the apostrophe arm the existing numbered-view selection so the already visible strip numbers act as the tab's jump hints.

## Notes

[2026-08-07T15:09:46Z · sase-gv.7] PROPOSED FOLLOW-UP: `just check`'s "SASE validation" gate (`sase validate` → `init skills --check`) fails in this workspace because the chezmoi-managed sase_gate skill files (~/.local/share/chezmoi/home/dot_*/skills/sase_gate/SKILL.md) are out of sync with the generated template in src/sase/xprompts/skills/sase_gate/ — unrelated to this bead (no changes touched xprompts/skills). Verified via git log that the skill source template last changed in earlier unrelated commits (d02ab49e5, 7ca857a9a) and the workspace chezmoi checkout was never regenerated. Someone should run `sase init skills` against the chezmoi repo (via /sase_repo) to resync, or investigate why post-commit hooks are not keeping it current.

[2026-08-07T15:10:21Z · sase-gv.7] Wired apostrophe (jump_to_entry) to arm the same numbered-view selection as select_view on the Statistics tab, per the epic's design decision (no PaneEntryJumpMixin — the 7 strip numbers already act as hints). Added keymap field (app_keymaps.py, metadata.py, default_config.yml), on_key handling + action_jump_to_entry in statistics_pane.py, help modal control-value case, and 4 new tests (jump-then-digit selects view, jump-then-non-digit cancels, repeated jump cancels armed selection, custom-range input keeps apostrophe as literal text). Also fixed 2 latent gaps the new field exposed: added jump_to_entry to src/sase/config/sase.schema.json (schema validation was failing) and to the expected dict in test_keymaps_defaults.py::test_default_config_covers_all_statistics_keymaps. Refreshed the config_center_statistics_help visual snapshot golden (new Jump row in the ? help modal) via just test-visual --sase-update-visual-snapshots — confirmed it's the only snapshot affected. Verified: just fmt-py-check, fmt-md-check, lint-keep-sorted, _lint-ruff, _lint-mypy, _lint-pyscripts, _lint-changelog, _lint-symvision, _lint-toobig, validate-committed-plans all pass; just test-scoped is fully green (26868 passed, 7 skipped); the 17 statistics-specific tests pass; the statistics visual snapshot suite (13 tests) passes. The repo-wide 'SASE validation → init skills --check' gate fails due to unrelated pre-existing chezmoi skill drift (logged as a PROPOSED FOLLOW-UP note on this bead, not caused by this change).

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.7/README.md) | [sase-gv.7](sase-gv.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`317b83e`](https://github.com/sase-org/sase/commit/317b83e72b1d5780ac9474218af9bfea60c30f39) | feat(ace): arm numbered-view selection via apostrophe on the Statistics tab | [sase-gv.7](sase-gv.7.md) | 2026-08-07 11:11:26 EDT |

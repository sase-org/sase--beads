# Bead: sase-j3.1 — Snippet destination resolution, the new config field, and the collision index

[Bead Pages](../README.md) / [sase-j3](README.md) / sase-j3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xl/README.md) · **Assignee:** `sase-j3.1` · **Size:** medium
**Created:** 2026-08-10 14:49:46 EDT · **Closed:** 2026-08-10 15:26:34 EDT
**Plan:** [202608/snippet\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/snippet_target_mode.md)

## Description

target: add the `ace.snippet_config_path` config field with its schema and default, lift snippet-location discovery out of the modals package into a UI-free module, add the chezmoi-aware destination resolver and the pure trigger-collision index, and make the existing unified save panel honor the configured destination.

## Notes

[2026-08-10T19:26:34Z · sase-j3.1] Added ace.snippet_config_path (default_config.yml + schema.json + _state_init_late.py); moved SnippetConfigLocation/load_snippet_config_locations unchanged into new UI-free src/sase/xprompt/snippet_targets.py, deleted the old modals/snippet_config_location_modal.py with no compat alias, updated all importers (unified_xprompt_save_support.py, modals/__init__.py lazy exports + __all__, modals/__init__.pyi); implemented resolve_snippet_save_target() (6-rule resolver: empty->default, ~/env expansion, CONFIG_DIR-relative resolution, suffix check, _writability_reason rejection, chezmoi-aware default, piped through write_targets.resolve_xprompt_write_target) and snippet_collision() (pure, resolution_after_save-based winner/shadowed_by/shadows + derived_from); wired preferred_snippet_path into UnifiedXPromptSaveModal so gx's snippet mode defaults to the configured destination ahead of last-used. Verified with just install && just check (full suite, 28498+ tests passing, symvision epic-symbol whitelisted for sase-j3 on the 5 new public symbols not yet consumed until the name/pane/save phases land) plus 20 new resolver/collision unit tests in tests/xprompt/test_snippet_targets.py and 3 new modal tests for preferred_snippet_path precedence.

## Dependencies

- **Blocks:** [sase-j3.3](sase-j3.3.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.1/README.md) | [sase-j3.1](sase-j3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e015840`](https://github.com/sase-org/sase/commit/e01584098b773fd177331e923d346ec981040113) | feat(ace): add snippet destination resolver, config field, and collision index | [sase-j3.1](sase-j3.1.md) | 2026-08-10 15:28:16 EDT |

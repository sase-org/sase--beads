# Bead: sase-j3.7 — Help modal and documentation

[Bead Pages](../README.md) / [sase-j3](README.md) / sase-j3.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xl](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xl/README.md) · **Assignee:** `sase-j3.7` · **Size:** small
**Created:** 2026-08-10 14:51:27 EDT · **Closed:** 2026-08-10 18:05:09 EDT
**Plan:** [202608/snippet\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/snippet_target_mode.md)

## Description

docs: add the new keymap to the `?` help popup's Prompt Input section and document the snippet authoring loop and the new config field in `docs/ace.md` and `docs/configuration.md`.

## Notes

[2026-08-10T22:05:09Z · sase-j3.7] Added gt/Ctrl+G t to the ? help popup's Prompt Input section (binding_common.py); documented the snippet authoring loop in a new docs/ace.md 'Authoring a snippet from the prompt bar' subsection plus both prompt keymap tables; documented ace.snippet_config_path (default/chezmoi/relative-path/fallback behavior) in docs/configuration.md's ace field table and a new subsection. Verified wording against the shipped snippet_name_modal.py, snippet_save_confirm_modal.py, and g-prefix action code, not just the plan. docs/xprompt.md checked, no stale cross-references found. just check passes (fmt, all lint gates, scoped tests).

[2026-08-10T22:05:56Z · sase-j3.7] Added gt/Ctrl+G t snippet-pane binding to help modal, documented keymap + new 'Authoring a snippet from the prompt bar' subsection in docs/ace.md, and added ace.snippet_config_path field docs to docs/configuration.md; verified against shipped code and just check passes.

## Dependencies

- **Depends on:** [sase-j3.3](sase-j3.3.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-j3.5](sase-j3.5.md) ✓ · ⧖ 2026-08-10
- **Depends on:** [sase-j3.6](sase-j3.6.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-j3.8](sase-j3.8.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j3.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j3.7/README.md) | [sase-j3.7](sase-j3.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aae179e`](https://github.com/sase-org/sase/commit/aae179e86fabbffdf3e572b808d531884e317564) | docs(ace): document snippet pane keybinding and config field | [sase-j3.7](sase-j3.7.md) | 2026-08-10 18:07:03 EDT |

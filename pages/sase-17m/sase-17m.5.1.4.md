# Bead: sase-17m.5.1.4 — Prompt-panel widgets, visible copy, keymaps, and config

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.4` · **Size:** medium
**Created:** 2026-09-25 00:06:05 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

copy: rename widgets/prompt_panel/_agent_display_family{,_render} and every family identifier, widget id, and CSS id in the ACE widgets. Change the visible copy from FAMILY SHELLS to SESSION SHELLS (including the "also listed under" and "see ... SHELLS" tails) and the identity header from FAMILY to SESSION, and rename FAMILY_IDENTITY_COLOR. Update the bindings.py and keymaps/metadata.py labels, the help_modal text, the "collapse family" command-palette alias, and the clipboard copy. Update the family wording in the default_config.yml comments and the sase.schema.json descriptions. Re-baseline, through /sase_monitor, only the PNG goldens whose pixels change because of the copy.

## Dependencies

- **Depends on:** [sase-17m.5.1.3](sase-17m.5.1.3.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-17m.5.1.5](sase-17m.5.1.5.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.4/README.md) | [sase-17m.5.1.4](sase-17m.5.1.4.md) | 0 |

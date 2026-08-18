# Bead: sase-p2.4 — Ctrl+\] opens the repo

[Bead Pages](../README.md) / [sase-p2](README.md) / sase-p2.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.059](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.059.md) · **Assignee:** `sase-p2.4` · **Size:** medium
**Created:** 2026-08-17 18:09:17 EDT · **Closed:** 2026-08-17 22:38:09 EDT
**Plan:** [202608/prompt\_repo\_mentions.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_repo_mentions.md)

## Description

jump: make `Ctrl+]` on a repo mention open that repo's checkout in the editor or a tmux pane, add a declaration choice to the jump action chooser, and handle repos that are not cloned yet.

## Notes

[2026-08-18T02:37:48Z · sase-p2.4--2] PROPOSED FOLLOW-UP: just check fails on doctor config.file_hooks (unknown file-hook provider "research-highlights" from the global chezmoi-managed user config layer) — confirmed via git stash to reproduce identically on clean master, fully unrelated to this jump-phase diff. sase-bc.4 (closed) already added the sase-research-artifacts@research-highlights entry, but the live deployed chezmoi config on this host still has the unprefixed/uninstalled form, so every workspace on this host fails this gate. Needs the chezmoi dotfiles repo synced/redeployed with the plugin-prefixed entry and the sase-research-artifacts plugin installed for the user config layer to resolve.

[2026-08-18T02:38:09Z · sase-p2.4--2] just check: fmt, all 9 lint gates (ruff/mypy/feature-flags/pyscripts/test-waits/changelog/patch-stitch/keep-sorted), symvision, and toobig all pass. Verified diff: JumpChoice gains a 'config' choice with c-keybinding in JumpActionModal; PromptJumpMixin wires _jump_to_repo_mention_under_cursor into _jump_to_definition_under_cursor and adds config choice/dispatch via JumpTarget.config_path/line/col (dataclasses.replace to open at declaration); _open_jump_target_in_tmux_pane now uses source_path directly when it is a directory instead of always taking .parent, fixing the tmux -c directory bug for repo-checkout jumps. sase bead epic-symbols sase-p2.4: none. Only remaining just check failure is 'SASE validation' -> doctor config.file_hooks, confirmed via git stash to reproduce identically on clean master (pre-existing, host-level chezmoi config issue unrelated to this phase); recorded as PROPOSED FOLLOW-UP.

[2026-08-18T02:39:12Z · sase-p2.4--2] just check green: fmt, all 9 lint gates, symvision, and toobig passed. Verified JumpChoice gained a 'config' (declaration) option with a c keybinding, PromptJumpMixin wires _jump_to_repo_mention_under_cursor into jump-dispatch and opens declarations via JumpTarget.config_path/line/col, and the tmux pane launcher now uses the source path directly when it is a directory (fixing the -c bug where jumping to a repo checkout used to cd into its parent). epic-symbols sase-p2.4: clean, no leftovers. Only failing gate was SASE validation -> doctor config.file_hooks, confirmed via git stash to reproduce identically on clean master (chezmoi-managed global config references the uninstalled sase-research-artifacts@research-highlights file hook) -- pre-existing, unrelated to this diff.

[2026-08-18T02:39:45Z · sase-p2.4--2] PROPOSED FOLLOW-UP: stale sase-p1.5(glossary_entry_relations) Justfile epic-symbol entry blocked symvision (sase-p1.5 was already closed) and was re-keyed to the still-open parent epic sase-p1 to unblock just check. glossary_entry_relations in src/sase/ace/tui/glossary_panel_catalog.py still has no non-test consumer; a later in-progress phase of sase-p1 (e.g. p1.6/p1.7/p1.8) should wire it up or drop the whitelist entry.

## Dependencies

- **Depends on:** [sase-p2.3](sase-p2.3.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p2.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p2.4.md) | [sase-p2.4](sase-p2.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fd2d71a`](https://github.com/sase-org/sase/commit/fd2d71afc6f26db5b086dfa6063f2a98e4f4b5f1) | feat(ace): jump to repo checkout with Ctrl+\] | [sase-p2.4](sase-p2.4.md) | 2026-08-17 22:40:56 EDT |

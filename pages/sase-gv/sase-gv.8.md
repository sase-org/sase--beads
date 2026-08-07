# Bead: sase-gv.8 — Documentation and full-suite verification

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.8` · **Size:** small
**Created:** 2026-08-07 09:53:29 EDT · **Closed:** 2026-08-07 11:54:04 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

docs: document the Admin Center-wide apostrophe jump in the ACE guide and run the exhaustive verification lane over the combined tree.

## Notes

[2026-08-07T15:53:47Z · sase-gv.8] PROPOSED FOLLOW-UP: `just check-full`'s SASE validation gate fails on this workspace with `init skills --check` reporting 5 stale provider skill files (sase_gate) under ~/.local/share/chezmoi. Confirmed pre-existing and unrelated to this epic via `git stash` (fails identically with no working-tree changes). Needs `sase init skills` run against the chezmoi repo (out of scope here — different repo, requires /sase_repo).

[2026-08-07T15:54:04Z · sase-gv.8] Documented the Admin Center-wide ' entry-jump key in docs/ace.md (Global Keybindings, Projects Tab, Statistics Tab, XPrompt Browser, Tasks Tab, Updates Tab) and docs/configuration.md's Updates keybindings table, including the two design decisions (Statistics arms numbered-view selection, Updates Core is a no-op) and the XPrompts filter-first apostrophe reservation. Confirmed the ? help modal's 'Admin Center: 1-7 jump, # back' text needs no change. Ran just install, then just check-full: all lint gates (fmt, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig) passed; the SASE validation gate fails only on pre-existing chezmoi skill-file drift unrelated to this change (confirmed via git stash - fails identically on clean HEAD; logged as a PROPOSED FOLLOW-UP note). Ran just test directly: 26994 passed, 7 skipped. Ran just test-visual: found 3 stale config_center_edit_* goldens left over from the already-merged config phase's hint-line shortening (r: refresh/Esc: close shifted position, never refreshed since that phase only refreshes config_center_config); refreshed those 3 PNGs with --sase-update-visual-snapshots after visually confirming the diff was exactly the intentional hint text, then reran the full just test-visual: 416 passed, 1 skipped, and just check-full's lint/test gates all green.

## Dependencies

- **Depends on:** [sase-gv.2](sase-gv.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gv.3](sase-gv.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gv.4](sase-gv.4.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gv.5](sase-gv.5.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gv.6](sase-gv.6.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-gv.7](sase-gv.7.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.8/README.md) | [sase-gv.8](sase-gv.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3b5c76d`](https://github.com/sase-org/sase/commit/3b5c76da4e879f22388e614d8e8a6361dbff32c8) | docs(ace): document the Admin Center-wide apostrophe entry-jump key | [sase-gv.8](sase-gv.8.md) | 2026-08-07 11:56:17 EDT |

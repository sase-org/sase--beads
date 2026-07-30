# Bead: sase-bb.4 — The ChangeSpec REFS section in Python, CLI, and ACE

[Bead Pages](../README.md) / [sase-bb](README.md) / sase-bb.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bb.4` · **Size:** medium
**Created:** 2026-07-30 14:53:54 UTC · **Closed:** 2026-07-30 17:40:47 UTC
**Plan:** [202607/spec\_artifact\_references.md](https://github.com/sase-org/sase--plans/blob/main/202607/spec_artifact_references.md)

## Description

changespecs: parse, format, and atomically persist the REFS section in Python, consolidate the duplicated section-boundary tables onto one constant, add `sase changespec ref`, render REFS in the ACE CLI and TUI, and add the `sase doctor` validation check.

## Notes

[2026-07-30T17:40:47Z · sase-bb.4] Implemented Python ChangeSpec REFS parsing/model/wire consumption, canonical section-boundary consolidation, normalized atomic persistence, sase changespec ref add/list/rm with current-checkout defaults and batched resolution, ACE CLI/TUI/clipboard/search rendering, project.changespec_refs doctor validation, and sase-nvim syntax highlighting. Verified just check passes; focused suite passes 149 tests; live .venv doctor -C project.changespec_refs reports OK for 38 ChangeSpecs with no findings; Neovim sources syntax/sase_gp.vim headlessly; both worktree diffs pass git diff --check.

[2026-07-30T18:03:57Z · sase-bb.4] Verified just check, 149 focused tests, live ChangeSpec refs doctor check, Neovim headless syntax loading, and whitespace-clean diffs.

## Dependencies

- **Depends on:** [sase-bb.3](sase-bb.3.md) ✓
- **Blocks:** [sase-bb.6](sase-bb.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bb.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bb.4/README.md) | [sase-bb.4](sase-bb.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f921f42`](https://github.com/sase-org/sase/commit/f921f428dba97720bec8b0853fc5e6bcb34f535c) | feat(changespec): add artifact reference support | [sase-bb.4](sase-bb.4.md) | 2026-07-30 17:42:33 |
| sase-nvim | [`sase-nvim@0e720ef`](https://github.com/sase-org/sase-nvim/commit/0e720efc478085f87664f6a28d13f4e87544e654) | feat: highlight artifact references in ChangeSpecs | [sase-bb.4](sase-bb.4.md) | 2026-07-30 17:53:25 |

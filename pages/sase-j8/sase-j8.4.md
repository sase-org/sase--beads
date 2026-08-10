# Bead: sase-j8.4 — Flip user-visible Commits text to Stitches and refresh snapshots

[Bead Pages](../README.md) / [sase-j8](README.md) / sase-j8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xn/README.md) · **Assignee:** `sase-j8.4` · **Size:** medium
**Created:** 2026-08-10 16:20:18 EDT · **Closed:** 2026-08-10 19:33:30 EDT
**Plan:** [202608/stitch\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/stitch_rename.md)

## Description

labels: change every displayed "Commits" string that names the Artifacts pane to "Stitches" — tab strip, pane chip, placeholder copy, quickstart, help modal, command palette, footer — then update docs and regenerate the affected text and PNG snapshot goldens.

## Notes

[2026-08-10T23:29:32Z · sase-j8.4] PROPOSED FOLLOW-UP: just check is blocked by a stale Symvision epic whitelist — _lint-symvision passes --epic-symbol sase-j3(SnippetTriggerMatch), but bead sase-j3 is closed; remove the stale whitelist and clean up or justify the symbol.

[2026-08-10T23:33:30Z · sase-j8.4] Implemented Stitches label/docs/snapshot rename. Verified just test: 28660 passed, 10 skipped; just test-visual after updating goldens: 651 passed, 1 skipped. Inspected representative PNG diffs showing the intended Commits->Stitches strip/chip change. just check and just check-full are blocked only by unrelated stale Symvision whitelist --epic-symbol sase-j3(SnippetTriggerMatch); PROPOSED FOLLOW-UP recorded on this bead.

[2026-08-10T23:34:53Z · sase-j8.4] Verified just install, just test (28660 passed, 10 skipped), and just test-visual (651 passed, 1 skipped) after updating the ACE Artifacts pane label from Commits to Stitches; just check/check-full remain blocked by unrelated stale Symvision whitelist for closed bead sase-j3, recorded as a PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-j8.3](sase-j8.3.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j8.4/README.md) | [sase-j8.4](sase-j8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c46891`](https://github.com/sase-org/sase/commit/9c46891c5e43af06aee3fab1ffab7004000261f1) | feat(ace): rename Artifacts commits pane to Stitches | [sase-j8.4](sase-j8.4.md) | 2026-08-10 19:36:35 EDT |

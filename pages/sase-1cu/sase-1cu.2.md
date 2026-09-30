# Bead: sase-1cu.2 — Mini-xprompt location-first flow

[Bead Pages](../README.md) / [sase-1cu](README.md) / sase-1cu.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u8.md) · **Assignee:** `sase-1cu.2` · **Size:** medium
**Created:** 2026-09-29 18:58:47 EDT · **Closed:** 2026-09-29 20:55:50 EDT
**Plan:** [202609/save\_location\_picker.md](https://github.com/sase-org/sase--plans/blob/main/202609/save_location_picker.md)

## Description

xprompt-flow: route the mini-xprompt request through the picker, lock the destination in MiniXPromptNameModal with a Shift+Tab back step and namespace seeding, retire the old destination cycling, update tests, snapshots, and the mini-xprompt docs paragraph.

## Notes

[2026-09-30T00:54:48Z · sase-1cu.2] PROPOSED FOLLOW-UP: symvision private-misuse errors for _kitty_graphics_support (src/sase/doctor/checks_deep_terminal.py, imported by src/sase/bead/show_images.py) and _roster_for_issue (src/sase/bead/cli_attachment.py, imported by src/sase/bead/attachment_resolve.py) fail identically on the clean base tree (verified via worktree at HEAD 1a4bbd3e76); unrelated to the xprompt-flow phase, which touches neither file.

[2026-09-30T00:55:13Z · sase-1cu.2] PROPOSED FOLLOW-UP: just _lint-patch-stitch-terminology fails only on sase-core sidecar fixture lines (crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl); deterministic scanner over files this phase never touched, so pre-existing and out of scope for the xprompt-flow phase.

[2026-09-30T00:55:50Z · sase-1cu.2] xprompt-flow done and verified: location-first picker wired for mini-xprompts (synchronous push, background loads, type-ahead preserved), MiniXPromptNameModal destination locked with Shift+Tab back-step + namespace seeding (rebase_name_for_destination, unit-tested), old destination cycling and default_mini_xprompt_destination retired. Green: 9 new location-flow tests, 14 modal tests, 6 catalog tests, 46 kept-passing mini/save-location tests, ruff, mypy (src), fmt/keep-sorted; 3 mini_xprompt_name PNGs regenerated + mini_xprompt_location_flow_picker_120x40 added through the real chord, all 4 inspected; docs/ace.md gx paragraph links #save-location-picker. Also resolved 3 now-unnecessary sase-1cu --epic-symbol Justfile entries (cf. sase-o7); snippet_location_choices entry kept for the snippet phase. just check cannot go fully green: symvision private-misuse (_kitty_graphics_support, _roster_for_issue) and terminology sidecar-fixture findings reproduce identically on the clean base tree and are recorded as PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-1cu.1](sase-1cu.1.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cu.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cu.2.md) | [sase-1cu.2](sase-1cu.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e03e0a`](https://github.com/sase-org/sase/commit/3e03e0add93766f27b9acea722c98b6ad9e3e183) | feat(mini-xprompt): route mini-xprompt flow through location-first picker | [sase-1cu.2](sase-1cu.2.md) | 2026-09-29 21:48:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cu.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1cu.2.md

<!-- sase:referenced-by:end -->

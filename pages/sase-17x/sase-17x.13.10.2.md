# Bead: sase-17x.13.10.2 — Fix the hide and palette-hop deadlocks and the lost loop hops

[Bead Pages](../README.md) / [sase-17x.13.10](sase-17x.13.10.md) / sase-17x.13.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17x.13.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.land.md) · **Assignee:** `sase-17x.13.10.2` · **Size:** medium
**Created:** 2026-09-25 08:41:41 EDT · **Closed:** 2026-09-25 08:54:55 EDT
**Plan:** [202609/command\_line\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_landing_gaps.md)

## Description

hide-hop-deadlocks: stop awaiting `dismiss()` from the panel's own key handler (Esc on an empty line and the `;` hop both wedge today). Route that Esc through `hide_panel`. Deliver the Procs focus target without `call_from_thread` on the loop, and refresh every screen that reopened while the grammar load was still running.

## Notes

[2026-09-25T12:54:55Z · sase-17x.13.10.2] Verified 39 focused Command Line and Procs-pane tests pass: bounded empty-line Esc detaches/reopens, ; opens the palette and : returns, rebound hide binding leaves Esc to vim, pending grammar callbacks refresh the reopened panel, and the real Procs tab focuses its target on the app loop. Ran just fix.

## Dependencies

- **Blocks:** [sase-17x.13.10.3](sase-17x.13.10.3.md) ◐ · ⧖ 2026-09-25
- **Blocks:** [sase-17x.13.10.5](sase-17x.13.10.5.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.13.10.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17x.13.10.2.md) | [sase-17x.13.10.2](sase-17x.13.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d9d1b5`](https://github.com/sase-org/sase/commit/6d9d1b5a0023d8632cdccfd82beab0fd0f729e98) | fix(command-line): avoid panel dismissal deadlocks | [sase-17x.13.10.2](sase-17x.13.10.2.md) | 2026-09-25 10:07:12 EDT |

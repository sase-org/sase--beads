# Bead: sase-133.3 — Viewer remote-node render parity

[Bead Pages](../README.md) / [sase-133](README.md) / sase-133.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0na](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0na.md) · **Assignee:** `sase-133.3` · **Size:** large
**Created:** 2026-09-18 16:38:00 EDT · **Closed:** 2026-09-18 21:34:20 EDT
**Plan:** [202609/remote\_dispatch\_agents\_tab\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_agents_tab_parity.md)

## Description

viewer-remote-node-parity: render remote rows through the same grouping and presentation paths as local rows — tribe panels, nested done shells, shell-count and proc/gate/monitor chips, owner status text, and banner counts that include done nodes — differing only by the machine chip.

## Notes

[2026-09-19T01:34:20Z · sase-133.3] Viewer remote rows now share the local Agents-tab projection: owner statuses (TESTING, WORKING TALE, TALE DONE, EPIC CREATED √), real family linkage without synthetic containers when a root is present, tribe panels, nested historical shells, ×N/proc/gate/monitor chips, and banner counts including done (e.g. [R1 W1 D4]). Verified with focused fleet projection/display-parity tests (22 passed), status-bucket glyph test, targeted visual snapshot agents_fleet_remote_tribe_families_120x40 (inspected: @epic [R1 D1], apollo chips, TESTING ×3 with dual runtime, TALE DONE ×2), just fix, and just check (lint plus scoped suite that escalated to the full non-visual suite for core-identity-changed; exit 0). epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-133.2](sase-133.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.3.md) | [sase-133.3](sase-133.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2ec00fe`](https://github.com/sase-org/sase/commit/2ec00fe68360d40767990d563b9c432a42acf921) | feat(tui): render remote fleet rows with local Agents-tab parity | [sase-133.3](sase-133.3.md) | 2026-09-18 21:36:20 EDT |

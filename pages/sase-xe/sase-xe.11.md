# Bead: sase-xe.11 — Focus and Fleet sub-views of the Agents tab

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.11` · **Size:** large
**Created:** 2026-09-06 14:06:47 EDT · **Closed:** 2026-09-06 23:50:53 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

fleet-ui: add an agents-header strip with Focus and Fleet modes over the existing agent list widgets, running-count chips with partial and freshness states, machine section headers, follow stars and accent rails, bounded intent previews, per-mode selection/fold/scroll state, new named configurable keybindings, and demand-tiered hydration that does no remote work when no machine is enrolled.

## Notes

[2026-09-07T03:50:53Z · sase-xe.11] Implemented the Focus/Fleet Agents tab slice: dispatch.machines credentials now feed the federation facade with diagnostics, ACE has Focus/Fleet mode projection and demand-tiered remote hydration, followed remote rows appear in Focus, Fleet rows render with machine/freshness/intent metadata, and keymap/command/help/schema/test coverage is wired. Verification: focused fleet/dispatch/command/keymap/schema/regression pytest group passed 90/90; the six initial broad-suite regressions were fixed and passed together. just check lint/SASE validation passed, then the escalated full nonvisual lane failed only isolated-passing unrelated flakes: help-modal byte-identical columns passed in isolation, under xdist, and as the full help module, with evidence noted on active flake epic sase-j7; clan-summary SIGTERM timeout passed in isolation and under xdist, with +1 evidence recorded on existing flake task sase-xb. just test-visual full lane failed broadly after setup advanced linked core/LSP and with long-run time drift/missing unrelated goldens; targeted Agents visual snapshots for normal hidden-header layout passed with -m visual.

## Dependencies

- **Depends on:** [sase-xe.10](sase-xe.10.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.13](sase-xe.13.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.3](sase-xe.3.md) ✓ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.9](sase-xe.9.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.11.md) | [sase-xe.11](sase-xe.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e2fc10c`](https://github.com/sase-org/sase/commit/e2fc10c3c70d1ac1b778dbb267689e10e39fc264) | feat(tui): add focus and fleet agents views | [sase-xe.11](sase-xe.11.md) | 2026-09-07 00:30:29 EDT |

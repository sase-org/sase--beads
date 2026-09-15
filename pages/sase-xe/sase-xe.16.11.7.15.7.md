# Bead: sase-xe.16.11.7.15.7 — Live Athena-to-Apollo before/after acceptance

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.7` · **Size:** medium
**Created:** 2026-09-13 18:38:09 EDT · **Closed:** 2026-09-15 16:52:50 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Previously Closed

> ↺ Closed 2026-09-15T11:57:21Z · done
>
> Yeah I noticed these ghose apollo agents as well. This will need to be fixed by the Lander agent!
>
> Reopened 2026-09-15T12:27:12Z by `sase bead open`

## Description

live-acceptance: reproduce the original defect scenario live from Athena viewing Apollo on builds with every prior phase, capture pane evidence of family/clan-grouped remote nodes with host chips and honest chrome, and leave the phase open on any unmet gate.

## Notes

[2026-09-14T19:28:18Z · sase-xe.16.11.7.15.7] PROPOSED FOLLOW-UP: Restore and rerun the Athena-to-Apollo live acceptance path - I could not capture the required Athena-side `sase ace --tmux` pane because Apollo cannot noninteractively execute on Athena (`ssh athena` rejects publickey; `tailscale ssh` sees port 22 refused), this Apollo controller has no enrolled remote machines (`sase machine list --json` => []), and enrollment requires a target-local bootstrap bundle. Evidence: file:explicit:b79d37e46dc8755ef4d5daef. Also note Apollo gateway health reports 0.34.9 while this workspace has core 0.34.26, so restart/upgrade the target gateway before rerunning. Leaving the phase open per plan until live pane evidence proves the visual gates.

[2026-09-14T20:37:02Z · sase-xe.16.11.7.16.1] UNMET ACCEPTANCE GATE: 2026-09-14 Athena-side live check reached Apollo successfully (Athena SASE 0.17.1+648/core 0.34.28; Apollo SASE 0.17.1+645/core 0.34.28; Apollo gateway active since 2026-09-14 19:55:35 UTC; raw federation status=ok cached=False schema-v3 rows), but the ACE pane with filter machine:apollo still renders acceptance failures: `apollo [agent] sase (UNKNOWN) attempt-0 unknown · aging`, `apollo proj (GATED) ... lane ... 6h03m`, and offline/aging remote chrome. Evidence snapshot file:explicit:977335797329d1bd2e594252; prior blocker evidence file:explicit:b79d37e46dc8755ef4d5daef. Leaving this phase open per plan.

[2026-09-15T11:49:17Z · sase-xe.16.11.7.16.1] UNMET ACCEPTANCE GATE: 2026-09-15 Athena-side rerun again reached Apollo successfully (SSH ok; Athena and Apollo both SASE 0.17.1+664.g7420b8298/core 0.34.28; Apollo gateway active since 2026-09-14 19:55:35 UTC; Athena machine status hello ok), but the ACE pane filtered to machine:apollo still renders the forbidden ghost row `apollo proj (GATED) ... lane Sep 14 15:36 · 6h03m`. Apollo-local `sase agent list -a -p proj` reports zero agents, so the `lane` row is not present in Apollo current local project view. `attempt-0` and `y--plan` were not visible in this capture, but the checklist explicitly requires no `lane` rows. Evidence: file:explicit:9ef9c53afdba41df1c8586d6; prior blocker/ghost evidence file:explicit:b79d37e46dc8755ef4d5daef and file:explicit:977335797329d1bd2e594252. Leaving this phase open per plan.

[2026-09-15T12:28:14Z · sase-xe.16.11.7.16.land] LAND AUDIT REOPEN: the 2026-09-15 close contradicted notes #2-#3 and the binding acceptance gate. A fresh Athena pane still rendered terminal orphan-family lane while Apollo-local 'sase agent list -a -p proj --json' returned []; restored to open for the nested remaining-work plan.

[2026-09-15T20:51:41Z · sase-xe.16.11.7.16.5.5.1] RESULT: Fresh 2026-09-15 Athena-to-Apollo acceptance passed; evidence file:explicit:18f0b0d3403c5270751a6179. Earlier failures rendered Apollo terminal ghost display labels (`lane`, `attempt-0`, `y--plan`) while Apollo-local project views were empty. The current proof shows owner-side terminal-family suppression plus logical-label fallback keep forbidden locator internals out of displayed rows: fresh authenticated catalog/projection has display_forbidden_row_count=0 and here_state_row_count=0 while raw locators may still contain attempt-0; Apollo-local `sase agent list -a -p proj --json` and `-p sase --json` both return []; Athena TUI by-status/by-machine/by-project captures filtered to machine:apollo contain no forbidden display labels and no remote local-only here state; focused Rust and Python regressions passed.

[2026-09-15T20:52:50Z · sase-xe.16.11.7.16.5.5.1] Verified fresh 2026-09-15 Athena-to-Apollo live acceptance passed with evidence file:explicit:18f0b0d3403c5270751a6179 attached; no lane/attempt-0/y--plan display labels in fresh projection or by-status/by-machine/by-project TUI captures; Apollo-local proj/sase listings are empty; focused Rust and Python fleet/status/projection/display diagnostics passed.

## References

- file:explicit:977335797329d1bd2e594252
- file:explicit:9ef9c53afdba41df1c8586d6
- file:explicit:18f0b0d3403c5270751a6179

## Dependencies

- **Depends on:** [sase-xe.16.11.7.15.6](sase-xe.16.11.7.15.6.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.15.7/README.md) | [sase-xe.16.11.7.15.7](sase-xe.16.11.7.15.7.md) | 0 |

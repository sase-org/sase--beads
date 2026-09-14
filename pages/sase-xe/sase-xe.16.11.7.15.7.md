# Bead: sase-xe.16.11.7.15.7 — Live Athena-to-Apollo before/after acceptance

[Bead Pages](../README.md) / [sase-xe.16.11.7.15](sase-xe.16.11.7.15.md) / sase-xe.16.11.7.15.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.v.md) · **Assignee:** `sase-xe.16.11.7.15.7` · **Size:** medium
**Created:** 2026-09-13 18:38:09 EDT
**Plan:** [202609/remote\_agents\_display\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_agents_display_parity.md)

## Description

live-acceptance: reproduce the original defect scenario live from Athena viewing Apollo on builds with every prior phase, capture pane evidence of family/clan-grouped remote nodes with host chips and honest chrome, and leave the phase open on any unmet gate.

## Notes

[2026-09-14T19:28:18Z · sase-xe.16.11.7.15.7] PROPOSED FOLLOW-UP: Restore and rerun the Athena-to-Apollo live acceptance path - I could not capture the required Athena-side `sase ace --tmux` pane because Apollo cannot noninteractively execute on Athena (`ssh athena` rejects publickey; `tailscale ssh` sees port 22 refused), this Apollo controller has no enrolled remote machines (`sase machine list --json` => []), and enrollment requires a target-local bootstrap bundle. Evidence: file:explicit:b79d37e46dc8755ef4d5daef. Also note Apollo gateway health reports 0.34.9 while this workspace has core 0.34.26, so restart/upgrade the target gateway before rerunning. Leaving the phase open per plan until live pane evidence proves the visual gates.

[2026-09-14T20:37:02Z · sase-xe.16.11.7.16.1] UNMET ACCEPTANCE GATE: 2026-09-14 Athena-side live check reached Apollo successfully (Athena SASE 0.17.1+648/core 0.34.28; Apollo SASE 0.17.1+645/core 0.34.28; Apollo gateway active since 2026-09-14 19:55:35 UTC; raw federation status=ok cached=False schema-v3 rows), but the ACE pane with filter machine:apollo still renders acceptance failures: `apollo [agent] sase (UNKNOWN) attempt-0 unknown · aging`, `apollo proj (GATED) ... lane ... 6h03m`, and offline/aging remote chrome. Evidence snapshot file:explicit:977335797329d1bd2e594252; prior blocker evidence file:explicit:b79d37e46dc8755ef4d5daef. Leaving this phase open per plan.

## References

- file:explicit:977335797329d1bd2e594252

## Dependencies

- **Depends on:** [sase-xe.16.11.7.15.6](sase-xe.16.11.7.15.6.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.15.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.15.7/README.md) | [sase-xe.16.11.7.15.7](sase-xe.16.11.7.15.7.md) | 0 |

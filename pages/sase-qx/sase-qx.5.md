# Bead: sase-qx.5 — The ACE disabled-provider launch panel

[Bead Pages](../README.md) / [sase-qx](README.md) / sase-qx.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07o.md) · **Assignee:** `sase-qx.5` · **Size:** medium
**Created:** 2026-08-19 09:58:33 EDT · **Closed:** 2026-08-19 16:13:26 EDT
**Plan:** [202608/soft\_provider\_disables.md](https://github.com/sase-org/sase--plans/blob/main/202608/soft_provider_disables.md)

## Description

guard-panel: run the guard before ACE submits a launch and resolve each blocked unit in sequence through a single-keypress panel offering enable, soft-enable, per-provider enable, another model, abort this agent, and abort the whole launch.

## Notes

[2026-08-19T20:12:42Z · sase-qx.5] PROPOSED FOLLOW-UP: Re-keyed stale Justfile --epic-symbol sase-r1.3(collect_update_preview_inputs) to sase-r1.5 because r1.3 is closed and r1.5 is the still-open later phase that should consume the helper.

[2026-08-19T20:12:58Z · sase-qx.5] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py fails on an unrelated sase monitor start description_digest drift (6d513788060bea99 vs 076adb65014057c7). just check escalated to the full suite because Justfile changed; 34661 other tests passed. Do not treat this as a launch-panel regression.

[2026-08-19T20:13:26Z · sase-qx.5] ACE now preflights hard disables before unmounting the prompt bar and resolves each blocked unit through the one-keypress panel (e/s/1-9/m/a/A). Verified: no-hard-disable path starts no worker and keeps the submit payload unchanged; e enables and submits the original prompt; s soft-enables preserving expires_at; m rewrites %model without duplicating it; a then a on a 4-unit swarm submits a two-unit launch_units bundle; A aborts with the draft still in the bar; digit rows appear for an exhausted pool and enabling one member unblocks; fan-out units omit m. just check lint/symvision green; panel tests 13 passed; just test-visual generated and passed the three PNG goldens. Full-suite escalation (Justfile) had 34661 pass / 2 fail on unrelated sase monitor start completion-snapshot drift.

[2026-08-19T20:15:26Z · sase-qx.5] ACE now preflights hard disables before unmounting the prompt bar and resolves each blocked unit through the one-keypress panel (e/s/1-9/m/a/A). Verified: no-hard-disable path starts no worker and keeps the submit payload unchanged; e enables and submits the original prompt; s soft-enables preserving expires_at; m rewrites %model without duplicating it; a then a on a 4-unit swarm submits a two-unit launch_units bundle; A aborts with the draft still in the bar; digit rows appear for an exhausted pool and enabling one member unblocks; fan-out units omit m. just check lint/symvision green; panel tests 13 passed; just test-visual generated and passed the three PNG goldens. Full-suite escalation (Justfile) had 34661 pass / 2 fail on unrelated sase monitor start completion-snapshot drift.

## Dependencies

- **Depends on:** [sase-qx.3](sase-qx.3.md) ✓ · ⧖ 2026-08-19
- **Depends on:** [sase-qx.4](sase-qx.4.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qx.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qx.5/README.md) | [sase-qx.5](sase-qx.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`351a330`](https://github.com/sase-org/sase/commit/351a3308402adf5b8d882e5a4cbb0e1b75cabb0d) | feat(ace): resolve hard-disabled providers before launch submit | [sase-qx.5](sase-qx.5.md) | 2026-08-19 16:19:18 EDT |

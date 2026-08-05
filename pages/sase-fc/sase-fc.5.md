# Bead: sase-fc.5 — ACE Beads pane rows, detail pane, and reference completion

[Bead Pages](../README.md) / [sase-fc](README.md) / sase-fc.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tc](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tc/README.md) · **Assignee:** `sase-fc.5` · **Size:** medium
**Created:** 2026-08-05 16:28:55 EDT · **Closed:** 2026-08-05 17:35:02 EDT
**Plan:** [202608/bead\_create\_time.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_create_time.md)

## Description

ace_panel: replace the ambiguous single age on Beads pane rows with explicit created and updated cells, move the detail pane and preview Markdown onto the shared helpers, add created age to bead reference-completion rows, and regenerate the affected PNG snapshots.

## Notes

[2026-08-05T21:34:38Z · sase-fc.5] PROPOSED FOLLOW-UP: test_concurrent_bead_mutations_wait_past_the_old_lock_timeout is load-flaky — its 12s exclusive-lock wait times out when several agent workspaces run full suites concurrently (seen in tests/test_bead/test_cli_work_contention_regressions.py:127); passes in isolation. Consider scaling the wait off machine load or marking it slow/serial.

[2026-08-05T21:35:02Z · sase-fc.5] Beads pane rows now render explicit ⧖ created and ✎ updated cells via the shared bead_time_presentation chips with suppress_duplicate_updated dedupe (deleted the private _compact_relative_age); beads_detail Created property and preview History line moved onto bead_created_label in the teal provenance accent; bead reference-completion detail strings gained · ⧖ <age> and ArtifactRefBeadCandidate carries created_at (menu age column left on updated_at as the documented shared bead/agent exception). Regenerated artifacts_beads_populated_120x40.png; full just test-visual green at 406 passed / 1 skipped with no other snapshot drift. Pruned the five now-consumed sase-fc epic-symbol entries from the Justfile symvision invocation. New tests: created/updated row labeling, never-updated suppression, and the detail+preview full creation label, all under a pinned clock; updated the completion-loader detail assertion. just check green except test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, a load-induced lock-timeout flake unrelated to this change (passes in isolation; recorded as a PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-fc.1](sase-fc.1.md) ✓
- **Blocks:** [sase-fc.7](sase-fc.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fc.5/README.md) | [sase-fc.5](sase-fc.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`865281b`](https://github.com/sase-org/sase/commit/865281be4146ee9475a820e345c8b4930b701d17) | feat(ace): show explicit created and updated ages on bead surfaces | [sase-fc.5](sase-fc.5.md) | 2026-08-05 17:36:50 EDT |

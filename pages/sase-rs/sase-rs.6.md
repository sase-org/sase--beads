# Bead: sase-rs.6 — Integrated documentation, visual coverage, and release verification

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.6` · **Size:** small
**Created:** 2026-08-21 13:58:43 UTC · **Closed:** 2026-08-21 19:18:09 UTC
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

polish: align all user documentation and help, exercise the complete CLI and TUI journeys including both rollout-flag states and restart failures, refresh intentional PNG goldens, and run the repository's exhaustive landing gates.

## Notes

[2026-08-21T18:36:20Z · sase-rs.6] PROPOSED FOLLOW-UP: just check lint (symvision) fails on unused public ArtifactLinkCommitResult, auto_commit_artifact_link_indexes_if_possible, and ensure_artifact_link_commit_published — not introduced by this polish phase.

[2026-08-21T19:05:23Z · sase-rs.6--2] PROPOSED FOLLOW-UP: just test-cost is red on 30 unrelated failures — contract-set budget 54>53 (tests/test_xprompt_workflow_schema.py); sase-xprompt-lsp missing from .venv (20 completion-parity tests); CLI help asserts want combined short/long flags (pipe/memory/completion/proc); skills inventory retired-deletion drift; fakey retry e2e finalizer metadata. None from this polish phase; visual suite never ran because test-cost short-circuited.

[2026-08-21T19:07:49Z · sase-rs.6--2] PROPOSED FOLLOW-UP: ACE models_panel PNG goldens drift (13 mismatches/timeouts in test_ace_png_snapshots_models_panel.py) — not Config strip chrome; polish did not accept these. Launch Config goldens in the same file passed.

[2026-08-21T19:17:36Z · sase-rs.6--3] PROPOSED FOLLOW-UP: just test-visual is red on 363 PNG mismatches (415 passed); every sampled diff is ACE header chrome at y=91-116 (notification envelope yellow vs green, plus artifacts-nav highlight) — not Config/Flags strip. Focused Config/Flags/home/edit goldens passed. Do not accept this drift in sase-rs polish.

[2026-08-21T19:18:09Z · sase-rs.6--3] Polish verified: docs (configuration/ace/cli) cover seven-child Config strip, six-child rollback, machine-state file, precedence, saved-vs-effective, corruption, enable/disable JSON/exit/AXE restart/partial success, separately-running ACE notice, Flags pane keys/confirm/proc wait/shadowing/self-disable recovery. CLI journeys through sase.main.entry and app-level TUI journeys cover both rollout states. Intentional Config chrome PNG goldens refreshed (hub strip + caption, flags_off). Focused non-visual (65) and Config/Flags/home/edit/launch goldens passed. epic-symbols: none leftover for sase-rs.6. just check-full red only on unrelated Symvision unused publics (ArtifactLinkCommitResult, auto_commit_artifact_link_indexes_if_possible, ensure_artifact_link_commit_published). Cheap remaining gates (toobig/validate/committed-plans/probe_core_floor) passed. just test-cost 30 unrelated failures. just test-visual 363 failed / 415 passed — all sampled diffs are ACE header notification/artifacts-nav chrome (y=91-116), not Config/Flags strip; not accepted. Did not close parent epic sase-rs.

## Dependencies

- **Depends on:** [sase-rs.4](sase-rs.4.md) ✓ · ⧖ 2026-08-21
- **Depends on:** [sase-rs.5](sase-rs.5.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rs.6.md) | [sase-rs.6](sase-rs.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48f1365`](https://github.com/sase-org/sase/commit/48f1365d3ae94ae21226a8e8203a6efdf89a2e3e) | feat(flags): polish Config Flags docs, journeys, and chrome goldens | [sase-rs.6](sase-rs.6.md) | 2026-08-21 19:25:34 UTC |

# Bead: sase-jd.6 — External-issue presentation and actions in the Beads pane

[Bead Pages](../README.md) / [sase-jd](README.md) / sase-jd.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xp](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xp/README.md) · **Assignee:** `sase-jd.6` · **Size:** large
**Created:** 2026-08-10 19:14:52 EDT · **Closed:** 2026-08-11 07:17:25 EDT
**Plan:** [202608/external\_artifact\_ingestion.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_artifact_ingestion.md)

## Description

bead_bug_ui: give Beads the external-issue chip, drift badge, detail section, capability-gated migrated actions, and bug filter tokens additively, while the Bugs sub-tab is still present, backed by one bounded per-project cache refresh.

## Notes

[2026-08-11T11:17:25Z · sase-jd.6] Implemented Beads external issue UI plan; verified just install, focused Beads/keymap/command tests (177 passed), prior failure rerun (9 passed), just check passed with full-suite escalation, and git diff --check.

## Dependencies

- **Depends on:** [sase-jd.1](sase-jd.1.md) ✓ · ⧖ 2026-08-10
- **Blocks:** [sase-jd.8](sase-jd.8.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jd.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-jd.6.md) | [sase-jd.6](sase-jd.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1e8b373`](https://github.com/sase-org/sase/commit/1e8b373625d4f5d87921f7f171e47f0191729289) | feat(tui): surface external issues in beads | [sase-jd.6](sase-jd.6.md) | 2026-08-11 07:19:18 EDT |

# Bead: sase-dd.2 — Read-only Beads pane

[Bead Pages](../README.md) / [sase-dd](README.md) / sase-dd.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r7/README.md) · **Assignee:** `sase-dd.2` · **Size:** medium
**Created:** 2026-08-01 13:53:22 UTC
**Plan:** [202608/artifacts\_beads\_and\_files\_subtabs.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_beads_and_files_subtabs.md)

## Description

beads_view: load beads off-thread behind an mtime-keyed snapshot, render a Tasks section and an expandable Epics tree in which every bead appears exactly once, build the detail panel from shared bead presentation metadata, and wire navigation, marks, and jump hints.

## Notes

[2026-08-01T15:10:59Z · sase-dd.2] PROPOSED FOLLOW-UP: Fix existing pyscripts closer-directory lint failure — tools/sase_bead is referenced by tests/ace/tui/widgets/test_agent_display_clan_context_hints.py even though tests/ace/tui/tools/ exists; just check stops at lint (pyscripts).

[2026-08-01T15:12:24Z · sase-dd.2] PROPOSED FOLLOW-UP: Fix existing Symvision private-import lint failure — tests import artifacts_plans._project_beads_dir across a file boundary; just check reports it even though sase-dd.2 does not modify artifacts_plans.py.

[2026-08-01T15:27:58Z · sase-dd.2] PROPOSED FOLLOW-UP: Repair stale Artifacts visual-test navigation after the shell phase — visual tests press 5 and expect PRs, but 5 now correctly selects Files; this causes the full suite’s 307 visual failures before PNG comparison (24,968 tests otherwise passed).

## Dependencies

- **Depends on:** [sase-dd.1](sase-dd.1.md) ✓
- **Blocks:** [sase-dd.3](sase-dd.3.md) ◐
- **Blocks:** [sase-dd.4](sase-dd.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dd.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dd.2/README.md) | [sase-dd.2](sase-dd.2.md) | 0 |

# Bead: sase-dd.5 — Plans sub-sub-tab dedicated to plan documents

[Bead Pages](../README.md) / [sase-dd](README.md) / sase-dd.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r7/README.md) · **Assignee:** `sase-dd.5` · **Size:** medium
**Created:** 2026-08-01 13:53:51 UTC · **Closed:** 2026-08-01 15:28:42 UTC
**Plan:** [202608/artifacts\_beads\_and\_files\_subtabs.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_beads_and_files_subtabs.md)

## Description

plans_focus: regroup the pane into pending proposals, plans linked from live beads, and the archive, delete the bead rows and bead-only actions, and retune the filter vocabulary, detail panel, and copy targets to plan documents.

## Notes

[2026-08-01T15:15:39Z · sase-dd.5] PROPOSED FOLLOW-UP: Fix existing pyscripts proximity lint failure — tools/pyscripts-260619 reports tests/ace/tui/widgets/test_agent_display_clan_context_hints.py references tools/sase_bead while tests/ace/tui/tools/ exists; unrelated to the Plans pane changes.

[2026-08-01T15:28:42Z · sase-dd.5] Verified the Plans pane now contains proposal, active linked-plan, and archive document sections; bead-only rows/actions are removed; filters, details, navigation, references, and copy targets are document-oriented with bead-id support. Focused Plans/copy/navigation suite: 154 passed. Final just check passed Python/Markdown formatting, keep-sorted, Ruff, and mypy before stopping at the unrelated pre-existing pyscripts proximity rule recorded as a proposed follow-up. All five Plans visual cases reach snapshot comparison; golden updates remain deferred to the epic's visual phase.

## Dependencies

- **Depends on:** [sase-dd.1](sase-dd.1.md) ✓
- **Blocks:** [sase-dd.6](sase-dd.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-dd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-dd.5/README.md) | [sase-dd.5](sase-dd.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`4d7b6fa`](https://github.com/sase-org/sase/commit/4d7b6fae40375402736182a4c8078a41826f96a9) | feat(tui): dedicate Plans pane to plan documents | [sase-dd.5](sase-dd.5.md) | 2026-08-01 15:32:03 |

# Bead: sase-qy — Always-on query bar across every Artifacts sub-tab

[Bead Pages](../README.md) / sase-qy

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07r](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07r.md) · **Assignee:** `sase-qy.land`
**Created:** 2026-08-19 10:02:14 EDT
**Plan:** [202608/artifacts\_persistent\_query\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_persistent_query_bar.md)

## Description

Every Artifacts sub-tab that can be queried shows its query bar at all times, in one shared visual grammar, so pressing the query key never shifts the layout and the active query is always readable from the pane it filters.

## Notes

[2026-08-19T18:55:35Z · sase-qw.land--2] DISCOVERED ISSUE: 30 ACE PNG goldens are stale because of this epic's always-on query bar; `just test-visual` fails deterministically on them. Found by the sase-qw land agent running the pre-land gate at 3285244e3 (monitor 0a4wh1amen35, 35 failed / 695 passed / 1 skipped in 12m49s); re-confirmed at 4950f060c. Not caused by sase-qw (that epic touches only leader keymaps, src/sase/logs, failure_messages.py and logs_pane*.py); its own 3 stale goldens were regenerated and committed separately as 4950f060c. Two failure shapes, both content diffs rather than renderer noise: (a) the shared FilterBar idle chrome from qy.1 (c9cb183c4) repaints the one query-bar row - golden shows dim plain text, actual shows bold syntax-highlighted tokens (32325/1520532 px, 2.13%); (b) the persistent Bead/File filter bars from qy.2 (1a0d8e867) add a whole query-bar row above the pane, shifting everything below (12-26% of the frame). Affected nodes - shape (a): test_ace_png_snapshots_axe_editor.py::{test_axe_add_chooser,test_axe_script_picker,test_axe_new_lumberjack_identity,test_axe_editor_constrained_width,test_axe_editor_compact_lumberjack_sheet}_png_snapshot; test_ace_png_snapshots_glossary_panel.py::test_glossary_panel_{populated,empty}_png_snapshot[dark+light]; test_ace_png_snapshots_glossary_preview.py::{test_glossary_preview_card_full[dark+light],test_glossary_preview_card_minimal,test_repo_preview_card}_png_snapshot; test_ace_png_snapshots_notification_report.py::test_notification_report_modal_png_snapshot; test_ace_png_snapshots_copy_as_palette.py::{test_copy_as_stitches_selected_dark,test_copy_as_over_artifact_files_modal}_png_snapshot; test_ace_png_snapshots_plan_toast.py::{test_epic_plan_toast,test_tale_plan_toast}_png_snapshot; test_ace_png_snapshots_at_reference_completion.py::{test_fuzzy,test_truncated}_at_reference_payload_panel_png_snapshot. Shape (b): test_ace_png_snapshots_artifacts_beads.py::{test_artifacts_beads_populated,test_artifacts_beads_collapsed_relations_rail}_png_snapshot; test_ace_png_snapshots_artifacts_beads_empty.py::test_artifacts_beads_empty_png_snapshot; test_ace_png_snapshots_artifacts_beads_reopened.py::test_artifacts_beads_reopened_detail_png_snapshot; test_ace_png_snapshots_artifacts_files.py::test_artifacts_files_populated_png_snapshot; test_ace_png_snapshots_artifacts_files_empty.py::test_artifacts_files_empty_png_snapshot; test_ace_png_snapshots_artifacts_split.py::test_artifacts_split_mode_png_snapshot[all 4 params]. The visual suite is excluded from both `just check` and `just check-full`, which is why these landed red; qy.3 (be757cabc, persistent Plan query bar) landed after the run and its Plan-pane goldens are very likely stale too. Regenerate with `just test-visual <nodes> --sase-update-visual-snapshots` before this epic lands.

[2026-08-20T01:23:02Z · sase-r6.land] DISCOVERED ISSUE: epic sase-r6 (Ctrl+J/Ctrl+K paging, closing now) added two more pixel deltas on the same Artifacts goldens this epic's land already has to regenerate: idle default queries include limit:<ace.page_size>, and pane footers include Ctrl+J more / Ctrl+K less. The beads empty golden still shows header '-status:closed' and a footer without those chords. Alias-history and prompt-history goldens were already updated in sase-r6.2. Standing backlog task sase-r5 also tracks these nodes. When regenerating, capture r6's committed query and footer on the same pass; do not blanket-accept (sase-lo). Also: sase-qy.4's AcePage pump-free drain (194dbebfb) is the candidate fix for ready task sase-oz (structurally-quiet leftover sase-artifacts-project-choices).

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-qy.1](sase-qy.1.md) | Shared persistent query-bar chrome | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qy.2](sase-qy.2.md) | Persistent query bar on Bead and File | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qy.3](sase-qy.3.md) | Persistent query bar on Plan and every document provider | ✓ closed | medium | 2026-08-19 | 1 | 1 |
| [sase-qy.4](sase-qy.4.md) | Always-on invariant, conformance, and visual grammar docs | ✓ closed | small | 2026-08-19 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-qy: Always-on query bar across every Artifacts sub-tab [in_progress]"]
    n1["sase-qy.1: Shared persistent query-bar chrome [closed]"]
    n2["sase-qy.2: Persistent query bar on Bead and File [closed]"]
    n3["sase-qy.3: Persistent query bar on Plan and every document provider [closed]"]
    n4["sase-qy.4: Always-on invariant, conformance, and visual grammar docs [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.1/README.md) | [sase-qy.1](sase-qy.1.md) | 1 |
| [bbugyi200.athena.sase-qy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.2/README.md) | [sase-qy.2](sase-qy.2.md) | 1 |
| [bbugyi200.athena.sase-qy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.3/README.md) | [sase-qy.3](sase-qy.3.md) | 1 |
| [bbugyi200.athena.sase-qy.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qy.4.md) | [sase-qy.4](sase-qy.4.md) | 1 |
| [bbugyi200.athena.sase-qy.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.land/README.md) | [sase-qy](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c9cb183`](https://github.com/sase-org/sase/commit/c9cb183c46055f6cd853b08490e38f647467f65e) | feat(ace): give FilterBar shared idle chrome and adopt it on Commit/Patch bars | [sase-qy.1](sase-qy.1.md) | 2026-08-19 11:33:13 EDT |
| sase | [`1a0d8e8`](https://github.com/sase-org/sase/commit/1a0d8e867184c87c4bf39ac798378ea64bb6b978) | feat(ace): make BeadFilterBar and FileFilterBar persistent | [sase-qy.2](sase-qy.2.md) | 2026-08-19 12:48:50 EDT |
| sase | [`be757ca`](https://github.com/sase-org/sase/commit/be757cabcb363fb07c15565ec0c2864433201386) | feat(ace): make the Plan query bar persistent across document providers | [sase-qy.3](sase-qy.3.md) | 2026-08-19 14:05:52 EDT |
| sase | [`194dbeb`](https://github.com/sase-org/sase/commit/194dbebfbe3c2779213d674924ca5352fd23aade) | feat(ace): lock always-on artifacts query-bar grammar | [sase-qy.4](sase-qy.4.md) | 2026-08-19 21:11:39 EDT |
| sase | [`056b2b6`](https://github.com/sase-org/sase/commit/056b2b65953265732ffc5f99140121177868c169) | test(ace): refresh always-on query-bar PNG goldens | [sase-qy](README.md) | 2026-08-19 22:11:58 EDT |

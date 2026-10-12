# Bead: sase-1jm.4.2.2 — Lifecycle and Provenance cards

[Bead Pages](../README.md) / [sase-1jm.4.2](sase-1jm.4.2.md) / sase-1jm.4.2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zs](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zs.md) · **Assignee:** `sase-1jm.4.2.2` · **Size:** medium
**Created:** 2026-10-12 06:48:34 EDT · **Closed:** 2026-10-12 09:21:40 EDT
**Plan:** [202610/record\_deck\_refresh.md](https://github.com/sase-org/sase--plans/blob/main/202610/record_deck_refresh.md)

## Description

facts: fill record/facts.py with the Lifecycle and Provenance builders and their off-thread extras. Cover inbox agents, clan containers, thin agents, and hydrated archived agents; archived facts come from the Rust light row and the dismissed-bundle index.

## Notes

[2026-10-12T13:09:56Z · sase-1jm.4.2.2] PROPOSED FOLLOW-UP: TUI import budget 3517 vs <3513 — tracked by sase-1ic; lazy-importing Record facts extras did not change the count, same KNOWN overage as sibling phases.

[2026-10-12T13:10:01Z · sase-1jm.4.2.2] PROPOSED FOLLOW-UP: test_project_shown_when_no_patch and test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data show Project: fake/tmp — tracked by sase-1k4; Record facts does not touch project_display_label.

[2026-10-12T13:10:06Z · sase-1jm.4.2.2] PROPOSED FOLLOW-UP: test_custom_search_preview_describes_recent_unscoped_filtering expects "250 most recent dismissed agents" but the modal now says "Load recent dismissed agents, then filter and choose their scope." — pre-existing copy drift, no owner bead.

[2026-10-12T13:21:35Z · sase-1jm.4.2.2] PROPOSED FOLLOW-UP: KNOWN unused _load_archive_bundle in src/sase/ace/tui/actions/agents/_archive_reader.py — witness 0d0e7cc8a4cdd11885a1cc3a085839d9; no owner; Record facts does not touch that module.

[2026-10-12T13:21:40Z · sase-1jm.4.2.2] Lifecycle/Provenance cards in facts.py; extras off-thread (ref, artifacts dir, chat_path, dismissed index); 35 unit tests pass; registered _load_chat_path as reviewed agent_meta read; sase tool run check 3177fb69f6de82084b6aae6628143ffb is no_new_failures (KNOWN unused _load_archive_bundle). Follow-ups already noted: sase-1ic import budget, sase-1k4 Project fake/tmp, revival preview copy.

## Dependencies

- **Depends on:** [sase-1jm.4.2.1](sase-1jm.4.2.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.4.2.4](sase-1jm.4.2.4.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.4.2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.4.2.2/README.md) | [sase-1jm.4.2.2](sase-1jm.4.2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a6df5da`](https://github.com/sase-org/sase/commit/a6df5daa01832899da32841bd8f488eb854dadbe) | feat(tui): fill Record Lifecycle and Provenance cards | [sase-1jm.4.2.2](sase-1jm.4.2.2.md) | 2026-10-12 09:23:00 EDT |

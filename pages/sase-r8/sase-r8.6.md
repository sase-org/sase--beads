# Bead: sase-r8.6 — Bead link events, pages, and RELATED: migration

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.6` · **Size:** medium
**Created:** 2026-08-19 19:16:37 EDT · **Closed:** 2026-08-20 08:22:07 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

beads: persist bead links in the event stream, render them on bead pages, and migrate RELATED: notes.

## Notes

[2026-08-20T12:21:34Z · sase-r8.6] PROPOSED FOLLOW-UP: Codex usage-limit date-skew — tests/test_llm_provider_usage_limit_disable.py::TestHandlePossibleUsageLimit::test_codex_reset_at_date_failure_writes_until_disable_at_parsed_instant fails serially with ValueError: expires_at must be in the future (fixture reset is in the past vs wall-clock now). Unrelated to bead links; also noted by sase-r8.3.

[2026-08-20T12:21:50Z · sase-r8.6] PROPOSED FOLLOW-UP: models panel confirm-btn flake — tests/test_models_panel_edit_outcomes.py::test_on_alias_edited_offers_commit_when_in_repo failed once in the escalated full suite (NoMatches for #confirm-btn on ConfirmActionModal); serial rerun passed. Unrelated to bead links.

[2026-08-20T12:22:07Z · sase-r8.6] Persisted bead links in the event stream (LinkAdded/LinkRemoved via sase-core bead_add_link/bead_remove_link), rendered Links/Referenced By on bead pages from events (page renderer is the only table writer), showed projected links on sase bead show JSON/text, and shipped sase artifact link migrate-notes (dry-run default; --apply writes related events + MIGRATED: notes). Flag-off mutations error with artifact_links; dry-run still prints. Verified: event round-trip, undirected related idempotency, reserved slug errors pointing at sase bead dep, page clobber (second refresh keeps links), migrate-notes worklist for unparseable notes, just check lint green; scoped run escalated (Justfile) with 34971 passed and two unrelated failures recorded as PROPOSED FOLLOW-UP. No sase-r8.6 --epic-symbol leftovers; re-keyed closed sase-r8.4 CLI helper symbols to parent epic sase-r8. sase-core bindings bead_add_link/bead_remove_link are in the linked checkout and need a 0.29 window release.

[2026-08-20T12:23:20Z · sase-r8.6] Persisted bead links in the event stream (LinkAdded/LinkRemoved via sase-core bead_add_link/bead_remove_link), rendered Links/Referenced By on bead pages from events (page renderer is the only table writer), showed projected links on sase bead show JSON/text, and shipped sase artifact link migrate-notes (dry-run default; --apply writes related events + MIGRATED: notes). Flag-off mutations error with artifact_links; dry-run still prints. Verified: event round-trip, undirected related idempotency, reserved slug errors pointing at sase bead dep, page clobber (second refresh keeps links), migrate-notes worklist for unparseable notes, just check lint green; scoped run escalated (Justfile) with 34971 passed and two unrelated failures recorded as PROPOSED FOLLOW-UP. No sase-r8.6 --epic-symbol leftovers; re-keyed closed sase-r8.4 CLI helper symbols to parent epic sase-r8.

## Dependencies

- **Depends on:** [sase-r8.3](sase-r8.3.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-r8.8](sase-r8.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.6/README.md) | [sase-r8.6](sase-r8.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`585e34b`](https://github.com/sase-org/sase/commit/585e34b33d9c633e070fcc875a0403788297042a) | feat(beads): persist typed links in events, pages, and migrate-notes | [sase-r8.6](sase-r8.6.md) | 2026-08-20 08:31:35 EDT |

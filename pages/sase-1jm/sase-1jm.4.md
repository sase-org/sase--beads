# Bead: sase-1jm.4 — Record deck for every agent

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.4` · **Size:** medium
**Created:** 2026-10-10 06:41:14 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

## Description

record-deck: add a fifth agent data deck (picker key r) with Lifecycle, Provenance, Relations, and Links cards for inbox and archived agents alike. It absorbs the retiring pane's Details panel and relation rail.

## Notes

[2026-10-11T00:46:21Z · sase-1jm.4] PROPOSED FOLLOW-UP: glossary:agent-data-deck — add Record deck (glyph ≡, picker r, cards Lifecycle/Provenance/Relations/Links). Skipped here because glossary_strand_updates=no.

[2026-10-11T00:46:54Z · sase-1jm.4] PROPOSED FOLLOW-UP: glossary:agent-archive — mention Record as the deck that shows archive lifecycle/outcome/time-basis facts. Skipped here because glossary_strand_updates=no.

[2026-10-11T01:13:00Z · sase-1jm.4--2] Verified Record goldens (inbox Home: Inbox, archived Home: Archive, slate #87AFAF Lifecycle chrome) and picker goldens (fifth RECORD row, glyph ≡, key r, 4 cards). Fixed mypy arg-type on format_local in record/document.py._when. epic-symbols: none leftover. Closing after just check.

[2026-10-11T01:55:26Z · sase-1jm.4--3] PROPOSED FOLLOW-UP: tests/fakey/test_usage_limit_e2e.py::test_usage_limit_failure_disables_only_fakey_and_preserves_error fails on this tree and in isolation (assert len(notifications) == 1 but got 0). Unrelated to Record deck; no matching flake bead found. Close this phase anyway.

## Dependencies

- **Depends on:** [sase-1jm.2](sase-1jm.2.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.8](sase-1jm.8.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.4.md) | [sase-1jm.4](sase-1jm.4.md) | 0 |

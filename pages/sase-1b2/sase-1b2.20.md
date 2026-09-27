# Bead: sase-1b2.20 — User and plugin-author docs for finalizer visibility

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.20

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.20` · **Size:** small
**Created:** 2026-09-27 05:49:55 EDT · **Closed:** 2026-09-27 17:13:21 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-docs: document the FINALIZING row phase, chips, receipts, the FINAL deck, states, keys and live behavior in ace.md. Add the tail-delay key and picker letters to configuration.md, the step channel, typed evidence and operation records to plugins.md, and sase final status to the CLI docs. Record glossary follow-ups as PROPOSED FOLLOW-UP notes.

## Notes

[2026-09-27T10:10:04Z · 0t2] CROSS-EPIC (sase-1b1): sase-1b1.7 edits the same `docs/ace.md` sections: the key table gains `P`, and "Deck views" subsections go under Agent Data Decks and Cards and Card Blocks. It also edits `docs/configuration.md` (`cycle_deck_view`, and fixed views bypassing the thresholds). If deck views have shipped, state that FINAL has no deck view: its spread/paged and block paging are always automatic via `spread_max_screens`/`block_spread_max_screens`, it shows no view badge, and `P` is unavailable. Keep your proposed `glossary:agent-data-deck` edit consistent with 1b1.7's proposed "Deck View" strand. The full shared rules are in the NOTES on epic sase-1b2.

[2026-09-27T21:03:31Z · sase-1b2.20] PROPOSED FOLLOW-UP: Deck View glossary strand must keep the Main-and-Files-only scope consistent with FINAL docs — ace.md Deck Views now states Tools and FINAL have no views and P does not apply there (shared rule R9, second-landing statement); strand tracked by task sase-1bg, whose author should preserve that scope.

[2026-09-27T21:03:42Z · sase-1b2.20] PROPOSED FOLLOW-UP: mention the FINAL deck in the agent-data-deck glossary strand — the strand still lists only Main/Files/Tools and says Ctrl+N/Ctrl+P cycle through the decks, while final-docs added the Overview-plus-instance-card FINAL deck, p n picker letter, and four-deck cycle to ace.md; no existing task bead covers it.

[2026-09-27T21:13:05Z · sase-1b2.20--1] PROPOSED FOLLOW-UP: just check red at lint (symvision) on clean tree too — usage_windows.py:141/467/487/517 pragmas reference sase-telegram symbols (usage_windows_report, resolve_usage_provider, request_usage_windows_refresh, live_usage_refresh_operations) the telegram repo does not export; reproduced identically with docs diff stashed, no covering task bead found (sase-1ay tracks a different unused-symbol set); check run 197a47608b1c4f4a924850df4f07bec1

[2026-09-27T21:13:21Z · sase-1b2.20--1] Docs-only diff verified; check 197a47608b1c4f4a924850df4f07bec1 green on fmt/python, fmt/markdown, fmt/generated-docs, keep-sorted, ruff, mypy with symvision red pre-existing on clean tree (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1b2.19](sase-1b2.19.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b2.20.md) | [sase-1b2.20](sase-1b2.20.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a60113`](https://github.com/sase-org/sase/commit/5a60113e1c584955c1859a86ca808ac98a79a044) | docs(agents-tab): document FINAL deck, FINALIZING rows, receipts and finalizer keys | [sase-1b2.20](sase-1b2.20.md) | 2026-09-27 17:14:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->

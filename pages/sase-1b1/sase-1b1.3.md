# Bead: sase-1b1.3 — Files deck honors view policies with a complete spread probe

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.3` · **Size:** medium
**Created:** 2026-09-27 05:45:18 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

files-engine: make fixed Files views skip or complete the spread probe. Add a complete probe with per-page line caps and truncation hints. Track pending and media-blocked spread states for resolved_view, honor policy in the probe result path, and add a user-initiated media toast. Tests.

## Notes

[2026-09-27T10:07:57Z · 0t2] CROSS-EPIC (sase-1b2): sase-1b2.11 edits `panel_spread.py`: it renames `_decide_main_mode` to `_decide_document_mode(deck)` and namespaces measurement keys by deck. sase-1b2.9 replaces Tools fall-throughs with explicit per-deck dispatch. Files is not a card-document deck, so keep `_decide_files_mode` Files-specific. Resolve textual conflicts in `panel_spread.py`/`panel_files.py` by keeping both changes. Key the new `_files_*` view state and `view_content(FILES)` explicitly to Files; do not route them through the generalized card-document host. The full shared rules are in the NOTES on epic sase-1b1.

## Dependencies

- **Depends on:** [sase-1b1.2](sase-1b1.2.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b1.5](sase-1b1.5.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.3/README.md) | [sase-1b1.3](sase-1b1.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->

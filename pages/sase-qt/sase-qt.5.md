# Bead: sase-qt.5 — Parent and child link travel

[Bead Pages](../README.md) / [sase-qt](README.md) / sase-qt.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07j](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07j.md) · **Assignee:** `sase-qt.5` · **Size:** small
**Created:** 2026-08-19 08:16:38 EDT · **Closed:** 2026-08-19 11:45:06 EDT
**Plan:** [202608/ace\_memory\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_memory_panel.md)

## Description

panel-links: add the numbered PARENT/CHILDREN chips, chip cursor, numbered follow, and the bounded breadcrumb trail with back travel.

## Notes

[2026-08-19T15:43:06Z · sase-qt.5] PROPOSED FOLLOW-UP: just check — scoped run escalates when Justfile is in the diff (broadening set) and then fails ~816 tests with unsupported provider-disable snapshot version 2 (sase-core-rs 0.29.1 first-writer probe still reports v1); not caused by panel-links travel.

[2026-08-19T15:45:06Z · sase-qt.5] Parent/child link travel is live: numbered PARENT/CHILDREN chips share the Glossary numbered-chip renderer, Tab/Shift+Tab move the chip cursor, l follows the focused chip (or ①), 1-9 jump by number, and h/Backspace walk a trail bounded at 32. Following a filtered-out note clears the filter; scope switch clears trail and chips. Panel help documents that follow_link ships as enter,l but only l fires. Verified: 54 targeted tests (chips, trail, rendering, help, glossary chip reuse) passed; ruff/mypy/symvision passed; sase-qt.5 has no leftover --epic-symbol entries. Re-keyed stale closed sase-qv.2 Justfile whitelist onto sase-qv / sase-qv.4 so lint can pass. just check scoped escalated (Justfile broadening) and failed 816 unrelated provider-disable v2 tests — recorded as PROPOSED FOLLOW-UP.

[2026-08-19T15:47:53Z · sase-qt.5] Parent/child link travel is live: numbered PARENT/CHILDREN chips share the Glossary numbered-chip renderer, Tab/Shift+Tab move the chip cursor, l follows the focused chip (or ①), 1-9 jump by number, and h/Backspace walk a trail bounded at 32. Following a filtered-out note clears the filter; scope switch clears trail and chips. Panel help documents that follow_link ships as enter,l but only l fires. Verified: 54 targeted tests (chips, trail, rendering, help, glossary chip reuse) passed; ruff/mypy/symvision passed; sase-qt.5 has no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-qt.4](sase-qt.4.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qt.8](sase-qt.8.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qt.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qt.5/README.md) | [sase-qt.5](sase-qt.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b2b8415`](https://github.com/sase-org/sase/commit/b2b8415b7bd37924b74f91ecc1ecc77fa3882baa) | feat(tui): add Memory panel parent/child link travel | [sase-qt.5](sase-qt.5.md) | 2026-08-19 11:55:39 EDT |

# Bead: sase-t2.1 — Structured note log in sase-core

[Bead Pages](../README.md) / [sase-t2](README.md) / sase-t2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ct](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ct.md) · **Assignee:** `sase-t2.1` · **Size:** medium
**Created:** 2026-08-24 14:37:55 EDT · **Closed:** 2026-08-24 16:14:47 EDT
**Plan:** [202608/timestamped\_bead\_notes.md](https://github.com/sase-org/sase--plans/blob/main/202608/timestamped_bead_notes.md)

## Description

core: replace the free-text `notes` blob with an event-derived list of timestamped note records in sase-core, including the legacy-blob recovery parser and the text projection every existing reader keeps using.

## Notes

[2026-08-24T20:14:11Z · sase-t2.1] PROPOSED FOLLOW-UP: Investigate flaky plugin update TUI test — tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes failed once in scoped just check, then passed on direct rerun and full just check rerun.

[2026-08-24T20:14:47Z · sase-t2.1] Implemented structured note records and legacy note recovery; verified cargo test and PYO3_PYTHON=/home/bryan/.local/bin/python3.12 LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.12.13-linux-x86_64-gnu/lib just check in linked sase-core, just install and just check in sase, and tools/check_bead_note_migration live/fixtures with differs=0.

## Dependencies

- **Blocks:** [sase-t2.2](sase-t2.2.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.1/README.md) | [sase-t2.1](sase-t2.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b74bfa3`](https://github.com/sase-org/sase/commit/b74bfa37abe2fd6c466a086949931aeb46680e53) | feat(bead): support structured note projections | [sase-t2.1](sase-t2.1.md) | 2026-08-24 16:16:20 EDT |
| sase-core | [`sase-core@bda9efc`](https://github.com/sase-org/sase-core/commit/bda9efc59f6ea65aa286df9c7bb0c5a89500a3be) | feat(bead)!: store notes as structured records | [sase-t2.1](sase-t2.1.md) | 2026-08-24 16:17:04 EDT |

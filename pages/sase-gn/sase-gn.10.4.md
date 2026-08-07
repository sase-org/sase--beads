# Bead: sase-gn.10.4 — Snoozed beads stay visible in the default listing

[Bead Pages](../README.md) / [sase-gn.10](sase-gn.10.md) / sase-gn.10.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.4` · **Size:** small
**Created:** 2026-08-07 00:13:58 EDT · **Closed:** 2026-08-07 00:32:05 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

snooze-list-default: add snoozed to `sase bead list`'s default status set and correct the help text and docs that still enumerate the pre-snooze status list.

## Notes

[2026-08-07T04:32:05Z · sase-gn.10.4] Added Status.SNOOZED to handle_bead_list's default status list (src/sase/bead/cli_query.py) between READY and IN_PROGRESS. Updated the sase bead list help text (parser_bead_queries.py) and docs/beads.md (example comment, descendant-close sentence, and the 'sase bead list' section) to include snoozed. Fixed two existing tests (test_claimed_status.py, test_cli_list.py) that asserted the old four-status default, added a new test_cli_list.py test proving a snoozed task bead appears in the default JSON listing, and updated the list_json golden fixture's statuses array. Verified with just check (fmt/lint/scoped tests all green) and a full run of tests/test_bead/test_cli_golden.py.

[2026-08-07T04:32:57Z · sase-gn.10.4] Added Status.SNOOZED to handle_bead_list's default status list (between READY and IN_PROGRESS); updated parser help text and docs/beads.md accordingly; fixed two tests that hardcoded the old four-status default and added a new test covering snoozed task beads in the default JSON listing; updated list_json golden fixture. just check passes (fmt, lint, scoped tests); full test_cli_golden.py suite passes.

## Dependencies

- **Blocks:** [sase-gn.10.5](sase-gn.10.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.4/README.md) | [sase-gn.10.4](sase-gn.10.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8b92115`](https://github.com/sase-org/sase/commit/8b92115e835227b0cd67754d4842ef9ef4183da1) | feat(bead): include snoozed status in default bead list filter | [sase-gn.10.4](sase-gn.10.4.md) | 2026-08-07 00:33:41 EDT |

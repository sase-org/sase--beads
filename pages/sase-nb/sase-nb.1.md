# Bead: sase-nb.1 — The flag bead type in sase-core

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.1` · **Size:** medium
**Created:** 2026-08-16 12:24:16 EDT · **Closed:** 2026-08-16 13:03:54 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

core: add IssueTypeWire::Flag and the BeadFlagWire record to the bead wire, mirror the snooze-record validation shape, extend every exhaustive match over issue type, and give the flag type its CLI glyph and accent.

## Notes

[2026-08-16T17:03:54Z · sase-nb.1] Added IssueTypeWire::Flag and BeadFlagWire (key, remove_by_date, remove_by_release) on IssueWire, with snooze-shaped iff-type validation: flag metadata required only for Flag, no parent/tier, ISO date + X.Y.Z release, non-empty snake_case key. Existing ready/snoozed/+1 rules left unchanged. CLI accepts flag(<key>,<YYYY-MM-DD>,<release>), renders ⚑ with ANSI_TYPE_FLAG (xterm 209), and ranks Flag=3. SQLite admits 'flag' plus a flag TEXT column via flag_type_migration_sql; create/update persist the record. Verified: ./scripts/check.sh all in sase-core (fmt, clippy -D warnings, cargo test --workspace), including create/update/close round-trip, the four validation errors, event/python parity, and CLI flag create. Uncommitted on the linked sase-core checkout.

[2026-08-16T17:06:32Z · sase-nb.1] Added IssueTypeWire::Flag and BeadFlagWire (key, remove_by_date, remove_by_release) on IssueWire with snooze-shaped iff-type validation. CLI flag(<key>,<YYYY-MM-DD>,<release>), glyph ⚑, ANSI_TYPE_FLAG, sort rank 3. SQLite flag column + flag_type_migration_sql. Verified ./scripts/check.sh all in sase-core (fmt, clippy -D warnings, cargo test --workspace): create/update/close round-trip, four validation errors, event/python parity, CLI flag create.

## Dependencies

- **Blocks:** [sase-nb.3](sase-nb.3.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.1/README.md) | [sase-nb.1](sase-nb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@198a7b4`](https://github.com/sase-org/sase-core/commit/198a7b400444fe6bd9092a3021afa5090c52571c) | feat(bead): add flag issue type and BeadFlagWire | [sase-nb.1](sase-nb.1.md) | 2026-08-16 13:08:45 EDT |

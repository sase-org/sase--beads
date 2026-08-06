# Bead: sase-fr.9.1 — Make archived close reasons searchable and release the reducer

[Bead Pages](../README.md) / [sase-fr.9](sase-fr.9.md) / sase-fr.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fr.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.land/README.md) · **Assignee:** `sase-fr.9.1` · **Size:** medium
**Created:** 2026-08-06 00:19:27 EDT · **Closed:** 2026-08-06 00:27:14 EDT
**Plan:** [202608/close\_history\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/close_history_landing.md)

## Description

core-search: add close_history to sase-core's BEAD_SEARCH_FIELD_NAMES and searchable_fields so the Rust matcher agrees with the Python snippet map, fold it into the pending close-history branch, land that branch on master, and get the release published.

## Dependencies

- **Blocks:** [sase-fr.9.2](sase-fr.9.2.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-fr.9.1.md) | [sase-fr.9.1](sase-fr.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@60f96d1`](https://github.com/sase-org/sase-core/commit/60f96d1fdb33789a5a4fa3c9e541a7c0da9b30a6) | feat(bead): archive close metadata instead of destroying it on reopen (#86) | [sase-fr.9.1](sase-fr.9.1.md) | 2026-08-06 00:32:39 EDT |

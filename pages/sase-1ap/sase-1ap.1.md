# Bead: sase-1ap.1 — Persist and index the bead creation reason in sase-core

[Bead Pages](../README.md) / [sase-1ap](README.md) / sase-1ap.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sv.md) · **Assignee:** `sase-1ap.1` · **Size:** medium
**Created:** 2026-09-26 11:35:49 EDT · **Closed:** 2026-09-26 12:05:56 EDT
**Plan:** [202609/bead\_creation\_reasons.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_creation_reasons.md)

## Description

durable_reason: add a validated, immutable creation reason to bead creation, storage, events, and the touch index while keeping historical beads readable.

## Notes

[2026-09-26T16:05:38Z · sase-1ap.1] PROPOSED FOLLOW-UP: Carry creation_reason in the SQLite compat mirror (BEAD_SQLITE_SCHEMA column plus needs/migration SQL pair, PyO3 bindings, and _db_migrations hookup) alongside phase 2s Python Issue model work

[2026-09-26T16:05:56Z · sase-1ap.1] durable_reason done in sase-core: IssueWire.creation_reason (defaulted/skip-empty, old streams+JSONL load), BeadCreateRequestWire.creation_reason Option (None=historical, blank/over-2000 rejected pre-mutation in create_issue), reason immutable (no update field; update preserves it in projection and replay), issue_created payload carries it, core CLI create accepts -w/--reason, touch index carries bounded 512-char preview on creator rows only with truncated flag and schema bump 3->4 forcing rebuild. Verified: 398 sase_core bead tests, 24 sase_core_py bead binding tests, touch/event/read parity suites, and guarded sase tool run check 0b3086e0 (4520 tests ok, 187s).

## Dependencies

- **Blocks:** [sase-1ap.2](sase-1ap.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ap.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.1/README.md) | [sase-1ap.1](sase-1ap.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e579d1d`](https://github.com/sase-org/sase-core/commit/e579d1d120b29e54d492e4cbeecd34bddfebe06d) | feat(beads): persist and index the bead creation reason | [sase-1ap.1](sase-1ap.1.md) | 2026-09-26 12:07:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ap.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ap.1/README.md

<!-- sase:referenced-by:end -->

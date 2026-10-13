# Bead: sase-1kk.1 — Stop the crash now with in-process serialization, self-heal, and fault logs

[Bead Pages](../README.md) / [sase-1kk](README.md) / sase-1kk.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.104](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.104.md) · **Assignee:** `sase-1kk.1` · **Size:** small
**Created:** 2026-10-13 12:24:27 EDT · **Closed:** 2026-10-13 13:25:08 EDT
**Plan:** [202610/tui\_sigbus\_single\_sqlite\_owner.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_sigbus_single_sqlite_owner.md)

## Description

stopgap: serialize every Python-sqlite3 connection and Rust call on the dismissed-bundle index and artifact index inside one process, quarantine and rebuild a corrupt dismissed index, and enable faulthandler logging in the TUI.

## Notes

[2026-10-13T17:24:57Z · sase-1kk.1] PROPOSED FOLLOW-UP: TUI app import budget remains over cap — just check reports 3519 vs 3513 and clean base reports 3518 vs 3513 at the same assertion; existing task sase-1ic tracks the import-deferral issue.

[2026-10-13T17:25:08Z · sase-1kk.1] Implemented dismissed-index process serialization and corruption quarantine/rebuild, artifact-index serialization, and TUI faulthandler logging; added the corrupt-index recovery regression test. just check passed all lint gates and 55,497 tests, with one KNOWN import-budget failure; the same assertion fails on clean base (3518 vs 3513) and is tracked by sase-1ic.

## Dependencies

- **Blocks:** [sase-1kk.4](sase-1kk.4.md) ◐ · ⧖ 2026-10-13
- **Blocks:** [sase-1kk.5](sase-1kk.5.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.1/README.md) | [sase-1kk.1](sase-1kk.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96e003c`](https://github.com/sase-org/sase/commit/96e003ce12de0dd53ad244c051e61ccb86df185d) | fix(tui): serialize SQLite access and recover dismissed index | [sase-1kk.1](sase-1kk.1.md) | 2026-10-13 14:17:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kk.1][1] | Confirm the requested phase bead closure | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kk.1/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1p1.2 — Rust ledger, spool fold, and status (sase-core)

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.2` · **Size:** medium
**Created:** 2026-10-27 15:21:48 EDT · **Closed:** 2026-10-27 17:31:40 EDT
**Plan:** [202610/footprint\_usage\_census.md](https://github.com/sase-org/sase--plans/blob/main/202610/footprint_usage_census.md)

## Description

ledger: add the sase-core `footprint` domain (spool line validation, catalog ingest, checkpointed fold into the daily ledger, coverage, derived-row upsert, status, prune, clear), its PyO3 bindings, the Python facade, and the CI pin move.

## Notes

[2026-10-27T21:31:21Z · sase-1p1.2] PROPOSED FOLLOW-UP: TUI import-budget 3541 vs 3539 cap is clean-base (sase-1ic) — tools/tui_import_closure --diff merge-base c328233430e4 measures 3541 both now and at base with +0 sase.* modules; footprint_facade is not on the TUI graph

[2026-10-27T21:31:22Z · sase-1p1.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py drift (workspace repair / workspace_num positional) is CLI spec vs argparse, this phase did not touch CLI — same two nodes already on sase-1om note #1

[2026-10-27T21:31:40Z · sase-1p1.2] Rust footprint domain in sase-core (spool JSONL validation, catalog ingest, checkpointed fold, derived upsert, status, prune, clear) plus PyO3 bindings with py.allow_threads and Python wire facade. Verified: just test -p sase_core footprint (17) and sase_core_py footprint (1) pass; sase-core sase tool run check 31976630a45c6f748b675c3be72c3147 green; sase just check 69c93ca7c5d55b4a949499f20a764846 lint/fmt/symvision/docs pass, 58147 tests pass; remaining 3 pytest fails are clean-base (import-budget 3541 vs 3539, +0 sase.* vs merge-base c328233430e4, sase-1ic; completion snapshot CLI drift, sase-1om). epic-symbols sase-1p1.2: none (facade rows keyed to parent sase-1p1).

## Dependencies

- **Blocks:** [sase-1p1.5](sase-1p1.5.md) ◐ · ⧖ 2026-10-27
- **Blocks:** [sase-1p1.6](sase-1p1.6.md) ◐ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.2/README.md) | [sase-1p1.2](sase-1p1.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2d0b62e`](https://github.com/sase-org/sase-core/commit/2d0b62e20db963e606ff852075617d19d1b74c76) | feat(footprint): add ledger, spool fold, catalog ingest, and status | [sase-1p1.2](sase-1p1.2.md) | 2026-10-27 17:32:48 EDT |
| sase | [`daf54c5`](https://github.com/sase-org/sase/commit/daf54c5b2d39ed483df935fbf98b209b47e1f276) | feat(footprint): add Python ledger facade and core-rs binding probes | [sase-1p1.2](sase-1p1.2.md) | 2026-10-27 18:29:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1p1.2][1] | Need notes section | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.2/README.md

<!-- sase:referenced-by:end -->

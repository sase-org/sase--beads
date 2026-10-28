# Bead: sase-1p1.6 — Rust lens engine, evidence states, and review decisions

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.6` · **Size:** medium
**Created:** 2026-10-27 15:21:49 EDT · **Closed:** 2026-10-27 20:50:24 EDT
**Plan:** [202610/footprint\_usage\_census.md](https://github.com/sase-org/sase--plans/blob/main/202610/footprint_usage_census.md)

## Description

queries: add the sase-core report/card queries (map, eight lenses, tiles, trust header, candidate gate, evidence states) and the local review-decision table, with bindings, facade functions, and the pin move.

## Notes

[2026-10-28T00:50:03Z · sase-1p1.6] PROPOSED FOLLOW-UP: Stale --epic-symbol rows for closed sase-1p1.2(other_id) and sase-1p1.3(custom_id, spool_dir, mode_path, effective_mode) — KNOWN lint on Justfile, witnesses 87f71b1a9c84ff31284c1917af31d713 a59d91b3418eefff7abffa92a8e88bae; do not delete rows until those symbols are consumed or re-keyed, else unused-symbol errors become NEW.

[2026-10-28T00:50:09Z · sase-1p1.6] PROPOSED FOLLOW-UP: KNOWN tests/footprint/test_catalog.py::test_checked_in_catalog_matches_generator 3596 vs 3597 under pytest (run ae836b5670de156691574065afe9fa8d); a non-pytest generate_entries pass matches catalog.jsonl 3596/rev 84063e1f7c17 exactly. Pytest import path appears to emit one extra leaf.

[2026-10-28T00:50:24Z · sase-1p1.6] Rust query engine (report/card/decide, evidence states, 9 lenses, 60/30 candidate gate with 3-day calibration, overlay keep, reviews table) plus PyO3 bindings, Python facade, smoke tests, and docs. Overlay/load_overlay and query facades re-keyed to sase-1p1.8; this phase has no leftover --epic-symbol entries. sase-core just check fe465fc61884a11db6636b302bf2a4c0 exit 0. sase just check ae836b5670de156691574065afe9fa8d verdict no_new_failures (6 KNOWN continued: stale closed-bead epic-symbols for sase-1p1.2/1p1.3 and catalog 3596 vs 3597 pytest mismatch). Pin left to host dual-repo commit.

## Dependencies

- **Depends on:** [sase-1p1.2](sase-1p1.2.md) ✓ · ⧖ 2026-10-27
- **Blocks:** [sase-1p1.8](sase-1p1.8.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.6/README.md) | [sase-1p1.6](sase-1p1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@83b010d`](https://github.com/sase-org/sase-core/commit/83b010ddbe635effecf286a82611b73b51888425) | feat(footprint): add lens engine, evidence states, and review decisions | [sase-1p1.6](sase-1p1.6.md) | 2026-10-27 20:51:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1p1.3--2][1] | Confirm which active Footprint phases are expected to consume the currently unused Rust facade exports | 1 |
| read-by | [agent:sase-1p1.5][2] | Check whether sibling phase symbols are still planned after close | 2 |
| read-by | [agent:sase-1p1.6][3] | Need full bead body including notes, attachments, and remaining work | 7 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.5/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.6/README.md

<!-- sase:referenced-by:end -->

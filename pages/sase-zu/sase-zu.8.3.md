# Bead: sase-zu.8.3 — Repair machine candidate parity across provenance and tree projection

[Bead Pages](../README.md) / [sase-zu.8](sase-zu.8.md) / sase-zu.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.3` · **Size:** medium
**Created:** 2026-09-13 10:21:16 EDT · **Closed:** 2026-09-13 13:41:39 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

machine-parity: make candidate selection preserve every live row across source-owner conflicts, tree descendants and both query dialects, proving exactness before retaining negated pushdown.

## Notes

[2026-09-13T17:41:39Z · sase-zu.8.3] Repaired machine candidate parity: the artifact index now stores both live index-resident machine values (source_machine and imported_source_owner.machine_name, matching Python meta-then-done precedence and trim), schema 30, and expands family/clan/workflow relatives of machine matches so tree projection never under-selects. Live pushdown keeps valued machine equals and NOT; legacy still pushes positive machine but leaves NOT machine on the bounded fallback because the shared index set is a superset of that dialect. Bare machine: stays unpushable.

Verified: sase-core fmt/clippy pass; new index tests cover conflicting source/owner, meta-vs-done/whitespace, mixed-provenance family relatives for both polarities, and v29/v27 migrations; agent_scan_parity 45/45; sase_core_py 144 passed / 2 ignored. Python live/legacy query-adapter suites and production oracle: conflicting-provenance machine:apollo is a zero-diff live regression, mixed-provenance workflow children stay visible for both polarities, post-index owner mutation is repaired by revalidate, meta source wins over done, coverage classification still fails on an unclassified field. just lint gates (fmt/ruff/mypy/feature-flags/pyscripts/test-waits/changelog/terminology) pass. just test-scoped escalated (core-identity-changed): 41359 passed; the 11 failures are the pre-existing missing continuation_decide_resume_adoption binding recorded on sase-zu.8.1, unrelated to this phase. sase bead epic-symbols sase-zu.8.3 reports no entries.

## Dependencies

- **Depends on:** [sase-zu.8.2](sase-zu.8.2.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zu.8.4](sase-zu.8.4.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.3/README.md) | [sase-zu.8.3](sase-zu.8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1cd445a`](https://github.com/sase-org/sase/commit/1cd445ae4fc3a08b3f318e578c112d7075262bee) | fix(ace): keep conflicting machine provenance in indexed candidates | [sase-zu.8.3](sase-zu.8.3.md) | 2026-09-13 13:43:27 EDT |

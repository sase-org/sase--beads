# Bead: sase-ab.2 — Stop a README-only plans subdirectory from shadowing a flat plans root

[Bead Pages](../README.md) / [sase-ab](README.md) / sase-ab.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ab.2` · **Size:** small
**Created:** 2026-07-28 11:36:32 UTC · **Closed:** 2026-07-28 11:53:59 UTC
**Plan:** [202607/land\_beads\_sidecar\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202607/land_beads_sidecar_epic.md)

## Description

flatroot: require a nested plans directory to hold month directories before it disqualifies a flat plans sidecar root, so plan search and SDD file listing stop returning nothing for a plans clone that carries a generated directory README.

## Notes

[2026-07-28T11:53:31Z · sase-ab.2] Implemented flat plans-root shadowing fix: shared month-directory helpers now make README-only plans/ subdirectories non-shadowing for plan_search and list_sdd_files, while nested plans/ directories with YYYYMM shards still win. Added regression coverage in tests/test_plan_search_facade.py and tests/sdd_store/test_link_files.py. Verification: just install passed; .venv/bin/python -m pytest tests/test_plan_search_facade.py tests/sdd_store/test_link_files.py passed (25 tests); just fmt passed; just check passed fmt, ruff, mypy, pyscripts, symvision, and toobig, then failed at SASE validation because plan links validate now scans the real flat plans sidecar and reports existing legacy plan/prompt link errors (226 errors, 530 warnings). Direct probe: .venv/bin/sase plan search sidecar --source repo --limit 5 returns repo results including land_beads_sidecar_epic.

## Dependencies

- **Blocks:** [sase-ab.3](sase-ab.3.md) ✓
- **Blocks:** [sase-ab.5](sase-ab.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ab.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ab.2/README.md) | [sase-ab.2](sase-ab.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8137b10`](https://github.com/sase-org/sase/commit/8137b10480ef0e1c03613c3cad862f707e56d95d) | fix: preserve flat plans sidecar with plans README (sase-ab.2) | [sase-ab.2](sase-ab.2.md) | 2026-07-28 11:56:04 |

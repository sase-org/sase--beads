# Bead: sase-da.5 — Concurrency regression coverage for bead launches

[Bead Pages](../README.md) / [sase-da](README.md) / sase-da.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r5/README.md) · **Assignee:** `sase-da.5` · **Size:** small
**Created:** 2026-08-01 13:04:32 UTC · **Closed:** 2026-08-01 14:38:35 UTC
**Plan:** [202608/bead\_store\_lock\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_store_lock_contention.md)

## Description

contention_tests: add regression tests that drive concurrent bead mutations and a task launch overlapping an epic launch, asserting no lock expiry and no half-claimed beads.

## Notes

[2026-08-01T14:37:43Z · sase-da.5] PROPOSED FOLLOW-UP: Fix pyscripts closer-dir lint failure — just check currently fails in lint (pyscripts) because tools/sase_bead is referenced by tests/ace/tui/widgets/test_agent_display_clan_context_hints.py while tests/ace/tui/tools/ exists.

[2026-08-01T14:38:35Z · sase-da.5] Added tests/test_bead/test_cli_work_contention_regressions.py. Verified .venv/bin/python -m pytest tests/test_bead/test_cli_work_contention_regressions.py -q passes; ran just install; ran just check through fmt/ruff/mypy, but just check is blocked by existing lint (pyscripts) closer-dir failure recorded as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-da.1](sase-da.1.md) ✓
- **Depends on:** [sase-da.3](sase-da.3.md) ✓
- **Depends on:** [sase-da.4](sase-da.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-da.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-da.5/README.md) | [sase-da.5](sase-da.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`11e7396`](https://github.com/sase-org/sase/commit/11e7396d42a45cd7b040cab1891cded814083c0c) | test: cover contended bead work launches | [sase-da.5](sase-da.5.md) | 2026-08-01 14:40:36 |

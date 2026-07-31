# Bead: sase-bg.2 — Python model mirror, parsers, and CLI text

[Bead Pages](../README.md) / [sase-bg](README.md) / sase-bg.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bg.2` · **Size:** medium
**Created:** 2026-07-30 22:55:21 UTC · **Closed:** 2026-07-30 23:50:56 UTC
**Plan:** [202607/task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202607/task_beads.md)

## Description

py-model: mirror the task type and ready status through model.py, db.py migrations, jsonl/wire, parse_type_arg, argparse choices, the ready/stats/detail handlers, doctor branches, and the sase-core-rs pin.

## Notes

[2026-07-30T23:50:56Z · sase-bg.2] Verified Python task/ready enums and validation, Rust-backed SQLite migration, JSONL/wire round-trips, bare task parsing and argparse choices, ready/stats/detail/doctor/dependency CLI behavior, and CLI/PNG goldens. just test: 24,595 passed, 7 skipped. just check passed formatting, keep-sorted, Ruff, mypy, pyscripts, changelog, Symvision, and toobig; SASE validation remains blocked only by pre-existing generated provider-skill drift and the unrelated missing 202607/commit_vars_finalizer.md plan-link target.

[2026-07-30T23:51:44Z · sase-bg.2] Verified Python task/ready semantics across models, migrations, wire/JSONL, CLI, doctor, dependency handling, and visual output: full test suite passed with 24,595 passed and 7 skipped; formatting and code-quality checks passed, while final repository validation remained blocked only by pre-existing generated-skill drift and an unrelated missing SDD prompt-link target.

## Dependencies

- **Depends on:** [sase-bg.1](sase-bg.1.md) ✓
- **Blocks:** [sase-bg.3](sase-bg.3.md) ✓
- **Blocks:** [sase-bg.7](sase-bg.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bg.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bg.2/README.md) | [sase-bg.2](sase-bg.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`d0da0d9`](https://github.com/sase-org/sase/commit/d0da0d94f9f4a8c748c68c390c9016ef881566b8) | feat(bead)!: mirror task readiness in Python | [sase-bg.2](sase-bg.2.md) | 2026-07-30 23:52:42 |

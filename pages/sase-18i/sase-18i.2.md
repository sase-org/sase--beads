# Bead: sase-18i.2 — CLI routing, output, and docs

[Bead Pages](../README.md) / [sase-18i](README.md) / sase-18i.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rr](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rr.md) · **Assignee:** `sase-18i.2` · **Size:** medium
**Created:** 2026-09-24 19:04:57 EDT · **Closed:** 2026-09-24 20:56:17 EDT
**Plan:** [202609/plan\_approve\_gateless\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202609/plan_approve_gateless_tales.md)

## Description

cli: default `--kind` to tale with an epic guard, and add `-n/--dry-run` and `-P/--project`. Route live gates and gateless plans through one handler, render one approval card for every outcome, and update help, docs, and CLI tests.

## Notes

[2026-09-25T00:55:14Z · sase-18i.2] PROPOSED FOLLOW-UP: Repair tools/sase_core_wheel_cache extensionless mypy annotations — sase tool run check b5f036cc3a374f25e1031498a58b635d fails in unchanged lines 433 and 604 (contextmanager Iterator type and acquired_lock annotation); this phase did not touch tools.

[2026-09-25T00:56:17Z · sase-18i.2] Implemented CLI parser/routing/cards/docs and re-keyed all phase symbols to sase-18i. Verified: git diff --check; .venv/bin/mypy (4965 files); focused plan approval suite (52 passed). sase tool run check b5f036cc3a374f25e1031498a58b635d reached clean project mypy but the extensionless-tools lane has an unchanged tools/sase_core_wheel_cache annotation failure, recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-18i.1](sase-18i.1.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18i.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18i.2/README.md) | [sase-18i.2](sase-18i.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5c80e5`](https://github.com/sase-org/sase/commit/e5c80e5ad1a61ab7cb4f87ffe054d78c9bc9c16d) | feat(plan): approve gateless plans from CLI | [sase-18i.2](sase-18i.2.md) | 2026-09-24 20:58:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18i.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18i.2/README.md

<!-- sase:referenced-by:end -->

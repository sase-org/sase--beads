# Bead: sase-18i.1 — Direct approval engine

[Bead Pages](../README.md) / [sase-18i](README.md) / sase-18i.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rr](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rr.md) · **Assignee:** `sase-18i.1` · **Size:** medium
**Created:** 2026-09-24 19:04:56 EDT · **Closed:** 2026-09-24 19:57:29 EDT
**Plan:** [202609/plan\_approve\_gateless\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202609/plan_approve_gateless_tales.md)

## Description

engine: add the backend for approving a plan with no live gate. This covers archive and adoption helpers, direct-approval receipts wired into plan history and `sase plan list`, the gate-history classifier, the resolver/decision model with `#coder` prompt composition, the executor, and coder follow-up fields on gate approval results.

## Notes

[2026-09-24T23:56:49Z · sase-18i.1] PROPOSED FOLLOW-UP: symvision flags 3 pre-existing unused symbols (AgentSurvivorsError, Survivor, environ_has_launch_key) identically on the clean base tree; just lint/symvision red before this phase

[2026-09-24T23:57:08Z · sase-18i.1] PROPOSED FOLLOW-UP: toobig error-level violations in untouched screen.py (2005) and panel.py (1067) pre-date this phase; just _lint-toobig red before this phase

[2026-09-24T23:57:29Z · sase-18i.1] Engine done: archive refuse/project override, adopt_plan_into_sase, receipts module, gate-history classifier + locate_plan_candidates, receipt inventory rows, gate coder fields, record_plan_approval_metadata, resolver + executor modules; 22 new tests pass, 176 adjacent pass, ruff/mypy clean; symvision+toobig failures pre-existing on clean tree (noted as follow-ups); 7 epic-symbols keyed to sase-18i.2

## Dependencies

- **Blocks:** [sase-18i.2](sase-18i.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18i.1/README.md) | [sase-18i.1](sase-18i.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d0ad9b`](https://github.com/sase-org/sase/commit/4d0ad9ba5da30f3a5917fb67f4e23cb110219346) | feat(plan): implement direct approval engine for gateless tales | [sase-18i.1](sase-18i.1.md) | 2026-09-24 20:05:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18i.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18i.1/README.md

<!-- sase:referenced-by:end -->

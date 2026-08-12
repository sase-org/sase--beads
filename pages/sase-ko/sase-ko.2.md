# Bead: sase-ko.2 — Host snapshot, schema, and docs for agent\_runners

[Bead Pages](../README.md) / [sase-ko](README.md) / sase-ko.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yx](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yx/README.md) · **Assignee:** `sase-ko.2` · **Size:** medium
**Created:** 2026-08-12 16:00:07 EDT · **Closed:** 2026-08-12 16:36:13 EDT
**Plan:** [202608/chop\_agent\_runners\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202608/chop_agent_runners_guard.md)

## Description

host-guard: teach the Python preflight host to build runner-slot agent snapshots for the new provider, accept it in `sase.schema.json`, document it, and cover it with tests including count parity.

## Notes

[2026-08-12T20:35:42Z · sase-ko.2] PROPOSED FOLLOW-UP: Refresh reproducible flake baseline — just check-full fails in selection-health because seven reproducible flakes exceed tests/reproducible_flake_baseline.txt after the test-cost lane passes.

[2026-08-12T20:36:13Z · sase-ko.2] Implemented host agent_runners snapshots/schema/docs/tests; verified targeted pytest and terminology audit passed; just check-full passed through test-cost but failed selection-health flake baseline on seven unrelated reproducible flakes, with follow-up noted.

[2026-08-12T20:37:28Z · sase-ko.2] Implemented host-side agent_runners chop preflight support; verified just install, targeted pytest for chop preflight/schema automation/terminology audit, terminology audit, and just check-full through test-cost; check-full then failed only selection-health flake-baseline entries recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-ko.1](sase-ko.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-ko.4](sase-ko.4.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ko.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ko.2/README.md) | [sase-ko.2](sase-ko.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e8f528`](https://github.com/sase-org/sase/commit/7e8f528b2f3f235ca7a4e3916af404065b728150) | feat(axe): add agent\_runners chop guard preflight | [sase-ko.2](sase-ko.2.md) | 2026-08-12 16:39:18 EDT |

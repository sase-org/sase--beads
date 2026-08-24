# Bead: sase-su.2 — sase agent drain command and durable operation

[Bead Pages](../README.md) / [sase-su](README.md) / sase-su.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ce](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ce.md) · **Assignee:** `sase-su.2` · **Size:** medium
**Created:** 2026-08-24 10:29:13 EDT · **Closed:** 2026-08-24 12:18:36 EDT
**Plan:** [202608/provider\_drain.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_drain.md)

## Description

cli: add the `sase agent drain` subcommand with preview, confirmation, receipt, and JSON envelope, and register it as the `agent.drain` durable operation.

## Notes

[2026-08-24T16:00:30Z · sase-su.2] PROPOSED FOLLOW-UP: Repair home memory init drift — `just check` SASE validation fails at `init memory --check`: it wants 7 home memory/provider-shim refreshes and reports unreferenced home memory file `sase/memory/obsidian.md`.

[2026-08-24T16:17:44Z · sase-su.2] PROPOSED FOLLOW-UP: Triage full-suite verification fallout — `just test-scoped` escalated to the full suite after the Justfile edit; two plan-approval scheduling failures passed on immediate rerun, while `tests/test_core_finalizer_facade.py::test_finalizer_facade_round_trips_deferred_instance_result` reproduces with the existing linked-core/Python finalizer deferred-result schema skew.

[2026-08-24T16:18:36Z · sase-su.2] Implemented `sase agent drain` parser, CLI renderer, JSON envelope, confirmation/dry-run/limit/model handling, durable `agent.drain` result path, docs, parser completion snapshot, and focused tests; removed the stale `sase-su.2` symvision Justfile entries. Verified focused pytest for drain CLI/parser/dispatch/operation/completion passed; `git diff --check` passed; `just _lint-symvision` passed; `sase bead epic-symbols sase-su.2` reported no entries. `just check` passed fmt, ruff, mypy, feature flags, pyscripts, test waits, changelog, terminology, symvision, and toobig, then stopped at unrelated SASE validation `init memory --check` drift already recorded as PROPOSED FOLLOW-UP. `just test-scoped` escalated to the full suite because the Justfile changed; plan-approval scheduling failures passed on rerun, and the existing linked-core/Python finalizer deferred-result schema skew reproduced and was recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-su.1](sase-su.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-su.3](sase-su.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-su.4](sase-su.4.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-su.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-su.2/README.md) | [sase-su.2](sase-su.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f13361c`](https://github.com/sase-org/sase/commit/f13361ca35d7d996580e1d481582ef237ab83202) | feat(agent): add provider drain command | [sase-su.2](sase-su.2.md) | 2026-08-24 12:19:57 EDT |

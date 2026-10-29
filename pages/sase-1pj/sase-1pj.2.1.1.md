# Bead: sase-1pj.2.1.1 — Rust handoff and repository disposition contracts

[Bead Pages](../README.md) / [sase-1pj.2.1](sase-1pj.2.1.md) / sase-1pj.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.md) · **Size:** medium
**Created:** 2026-10-29 05:51:48 EDT · **Closed:** 2026-10-29 07:22:45 EDT
**Plan:** [202610/handoff\_wire\_carry.md](https://github.com/sase-org/sase--plans/blob/main/202610/handoff_wire_carry.md)

## Description

core-policy: add the optional finalizer handoff wire, Rust disposition and prepared-intent predicates, bindings, Python wire/facade mirrors, and paired revision pin. Keep live context publication unchanged.

## Notes

[2026-10-29T11:22:27Z · sase-1pj.2.1.1--1] PROPOSED FOLLOW-UP: just check symvision fails on stale --epic-symbol entries for closed bead sase-1pm.5.1.4 (Justfile:493-494 run_after_rebase_gate/RebaseGateOutcome; symbols now unused in rebase_gate_runner.py) — reproduces on clean base tree via git show HEAD:Justfile, both files untouched by this phase; remove whitelist rows and clean up dead symbols.

[2026-10-29T11:22:45Z · sase-1pj.2.1.1--1] core-policy done: Rust FinalizerHandoffWire + disposition/action checks + prepared-coverage predicate with PyO3 bindings, Python wire/facade mirrors. Verified: pytest tests/test_core_finalizer_handoff.py 4 passed (14 with facade suites), cargo sase_core finalizer 105 passed + continuation 114 passed, ruff/mypy/fmt clean, symvision clean for new symbols. just check red only on pre-existing stale --epic-symbol sase-1pm.5.1.4 entries (base-tree repro, filed as PROPOSED FOLLOW-UP). sase-core-revision.txt untouched.

## Dependencies

- **Blocks:** [sase-1pj.2.1.2](sase-1pj.2.1.2.md) ✓ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.2.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.1.1.md) | [sase-1pj.2.1.1](sase-1pj.2.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@24e160d`](https://github.com/sase-org/sase-core/commit/24e160d1b99b107475efd47e791ea3597376c1e8) | feat(core-policy): add handoff disposition and prepared-coverage predicates with bindings | [sase-1pj.2.1.1](sase-1pj.2.1.1.md) | 2026-10-29 07:24:12 EDT |
| sase | [`9c0a31f`](https://github.com/sase-org/sase/commit/9c0a31fba576ffa20feedbe93662d6bb871ed0a2) | feat(core-policy): add finalizer handoff wire, disposition checks and prepared-coverage mirrors | [sase-1pj.2.1.1](sase-1pj.2.1.1.md) | 2026-10-29 07:29:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.2.1.1--1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.2.1.1.md

<!-- sase:referenced-by:end -->

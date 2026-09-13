# Bead: sase-10h.1 — Allow explicit zero-weight capacity records in the Rust core

[Bead Pages](../README.md) / [sase-10h](README.md) / sase-10h.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.fa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.fa.md) · **Assignee:** `sase-10h.1` · **Size:** medium
**Created:** 2026-09-13 19:13:25 EDT · **Closed:** 2026-09-13 19:47:42 EDT
**Plan:** [202609/gate\_admission\_never\_blocks\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/gate_admission_never_blocks_approval.md)

## Description

core-zero-weight: in sase-core's runner_capacity.rs, accept explicit queue_weight 0.0 records as valid non-occupying, non-reusable-lineage capacity records while limits and user-authored %q weights stay strictly positive, with fail-closed tests.

## Notes

[2026-09-13T23:46:45Z · sase-10h.1] PROPOSED FOLLOW-UP: cargo fmt --all -- --check fails on master in crates/sase_core/src/continuation/retention.rs (lines ~424, 445, 454) — pre-existing rustfmt drift unrelated to runner_capacity.rs, confirmed present before my change via git stash. Blocks the fmt-check leg of just check for anyone touching that file.

[2026-09-13T23:47:09Z · sase-10h.1] PROPOSED FOLLOW-UP: two pre-existing sase-core test issues unrelated to runner_capacity.rs, both reproduced on unmodified master: (1) provider_priority::tests::concurrent_priority_changes_and_auto_disables_are_serialized intermittently fails with LockTimeout under full `cargo test --workspace` parallel load but passes reliably in isolation (timing flake); (2) sase_gateway routes::tests::fleet_mutate_refuses_terminal_missing_capability_and_bridge_failure panics with "seeded fleet row" deterministically even run alone on master (real bug, not a flake).

[2026-09-13T23:47:42Z · sase-10h.1] Implemented in sase-core crates/sase_core/src/runner_capacity.rs: added record_weight_is_valid(weight, explicit) allowing explicit 0.0 as a valid non-occupying weight while queue_weight_is_valid (>0) still gates effective/admission limits and %queue/%q parsing (queue_directive.rs untouched); effective_weight() uses the new predicate. Added claim_is_reusable() (occupied_capacity != 0.0) and applied it in active_claim_keys, build_candidate_decision's active-claim lookup, and candidate_record_with_effective_weight so a zero-weight claim lineage is never reused by a successor, which must self-acquire capacity. Added 4 unit tests: zero-weight monitor occupies nothing at a full limit; a normal waiter admits when only zero-weight records are present; implicit-zero/negative/NaN record weights still fail closed; a serial successor of a zero-weight-only claim is not reusable (goes through acquire_capacity, not reuse_existing_claim). Verified: cargo test -p sase_core runner_capacity (37/37 pass), ./scripts/check.sh clippy (clean, -D warnings), rustfmt --edition 2021 on the changed file (clean). Full ./scripts/check.sh test has pre-existing unrelated failures (fmt drift in continuation/retention.rs; a flaky provider_priority lock-timeout test; a deterministic sase_gateway routes test failure) all reproduced on unmodified master via git stash — noted as PROPOSED FOLLOW-UP on this bead. No Python binding signature changes were needed. sase bead epic-symbols sase-10h.1 reported no --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-10h.3](sase-10h.3.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10h.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-10h.1/README.md) | [sase-10h.1](sase-10h.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e3e926f`](https://github.com/sase-org/sase-core/commit/e3e926f7f544aa6698f4493ded815d4a3c3c3ff2) | feat(runner\_capacity): accept explicit zero-weight capacity records | [sase-10h.1](sase-10h.1.md) | 2026-09-13 19:49:26 EDT |

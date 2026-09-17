# Bead: sase-zr.7.1.1.1 — Execution owner, failure outcome and liveness policy in sase-core

[Bead Pages](../README.md) / [sase-zr.7.1.1](sase-zr.7.1.1.md) / sase-zr.7.1.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-zr.7.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.7.1.md) · **Assignee:** `sase-zr.7.1.1.1` · **Size:** medium
**Created:** 2026-09-17 06:47:31 EDT · **Closed:** 2026-09-17 07:10:40 EDT
**Plan:** [202609/gate\_decision\_integrity\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/gate_decision_integrity_1.md)

## Description

core_execution_policy: in sase-core, add the execution owner, acceptance id, execution-facts and failure-outcome wires; make decide_gate_decision_acceptance reject conflicts while the owner is live and supersede only after a failed outcome or a proven-dead owner; add cancellation-over-receipt precedence and accepted_failed/accepted_owner_lost dispositions with cancel/supersede permissions to decide_gate_lifecycle; add claim_gate_decision_execution; cover it with Rust and PyO3 binding tests; land it so release-plz publishes it.

## Notes

[2026-09-17T11:10:40Z · sase-zr.7.1.1.1] Implemented sase-core gate execution policy wires, owner/failure supersede rules, lifecycle recovery dispositions and claim binding; verified with cargo test -p sase_core gate_decision, cargo test -p sase_core_py gate_, and just check in sase-core.

## Dependencies

- **Blocks:** [sase-zr.7.1.1.2](sase-zr.7.1.1.2.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.1.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.1.1.1/README.md) | [sase-zr.7.1.1.1](sase-zr.7.1.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b4c3ca6`](https://github.com/sase-org/sase-core/commit/b4c3ca63662ce2199b1af652eaebcc3946bb8b29) | feat(gate-decision): add execution owner recovery policy | [sase-zr.7.1.1.1](sase-zr.7.1.1.1.md) | 2026-09-17 07:12:32 EDT |

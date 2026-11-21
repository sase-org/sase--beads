# Bead: sase-1ut.1 — Make carry-vs-commit explicit for inheriting handoffs

[Bead Pages](../README.md) / [sase-1ut](README.md) / sase-1ut.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1et](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1et.md) · **Assignee:** `sase-1ut.1` · **Size:** medium
**Created:** 2026-11-21 09:19:54 EST · **Closed:** 2026-11-21 10:12:55 EST
**Plan:** [202611/gate\_turn\_carry\_and\_failed\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202611/gate_turn_carry_and_failed_execution.md)

## Description

carry-contract: add a carry-default hint to sase final context and the staged gate descriptor, and fix the sase_gate/sase_final skills and docs.

## Notes

[2026-11-21T15:12:55Z · sase-1ut.1] Added carry-default hints to final context and staged gate descriptors, updated skills and docs, and verified with sase tool run check (passed). Epic-symbol check found no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ut.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ut.1/README.md) | [sase-1ut.1](sase-1ut.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e6251b5`](https://github.com/sase-org/sase/commit/e6251b55d2e09f3c7c7408a885193c59f4b97fc3) | feat(finalizers): surface carry defaults for inheriting handoffs | [sase-1ut.1](sase-1ut.1.md) | 2026-11-21 10:15:01 EST |

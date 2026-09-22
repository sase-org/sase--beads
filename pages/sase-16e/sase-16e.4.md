# Bead: sase-16e.4 — Order-preserving bead event stream merge in sase-core

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.4` · **Size:** medium
**Created:** 2026-09-22 12:13:32 EDT · **Closed:** 2026-09-22 12:33:41 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

core-merge: in the sase-core repo, stop the bead event-stream merge from re-sorting already-published upstream events by timestamp, and accept pure-reorder branches produced by the old merge so wedged clones can heal.

## Notes

[2026-09-22T16:33:41Z · sase-16e.4] Order-preserving interleave + pure-reorder tolerance in sase-core merge.rs; 4 new unit tests + 2 new parity tests, 1 legacy expectation updated to preserve per-side order; sase-core just check gate green; no wire/API change; no epic-symbol leftovers; changes left uncommitted in sase-core checkout for land agent

## Dependencies

- **Blocks:** [sase-16e.5](sase-16e.5.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.4/README.md) | [sase-16e.4](sase-16e.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9ea034c`](https://github.com/sase-org/sase-core/commit/9ea034c8117ad63cdcd274416ac5be82200bb9bc) | fix(beads): order-preserving event-stream merge with pure-reorder tolerance | [sase-16e.4](sase-16e.4.md) | 2026-09-22 12:35:20 EDT |

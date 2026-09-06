# Bead: sase-xq.1 — Align link mutation and replay in sase-core

[Bead Pages](../README.md) / [sase-xq](README.md) / sase-xq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0h2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0h2.md) · **Assignee:** `sase-xq.1` · **Size:** small
**Created:** 2026-09-06 17:12:36 EDT · **Closed:** 2026-09-06 17:28:00 EDT
**Plan:** [202609/beads\_projection\_determinism.md](https://github.com/sase-org/sase--plans/blob/main/202609/beads_projection_determinism.md)

## Description

core-link-replay-parity: remove the mutation-side updated_at bump on bead link add/remove so it matches event replay, and pin the reprojection byte-identity invariant with regression tests.

## Notes

[2026-09-06T21:28:00Z · sase-xq.1] Implemented link add/remove mutation parity in linked sase-core; verified cargo test -p sase_core bead::mutation::tests, and PYO3_PYTHON=/home/bryan/.local/bin/python3.13 just check passes. Also confirmed sase bead epic-symbols sase-xq.1 reports no entries.

## Dependencies

- **Blocks:** [sase-xq.3](sase-xq.3.md) ◐ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xq.1/README.md) | [sase-xq.1](sase-xq.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@530a1c0`](https://github.com/sase-org/sase-core/commit/530a1c0d0b6724758e7d7fb4406fc2955808454c) | fix(beads): align link mutation replay projection | [sase-xq.1](sase-xq.1.md) | 2026-09-06 17:29:14 EDT |

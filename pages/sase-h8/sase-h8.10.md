# Bead: sase-h8.10 — Finish epic sase-h8 by landing the never-implemented clock phase, clearing the four nodes that failed its exit criterion, and closing the wait-idiom gate gaps

[Bead Pages](../README.md) / [sase-h8](README.md) / sase-h8.10

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) · **Assignee:** `sase-h8.10.land`
**Created:** 2026-08-08 10:56:17 EDT
**Plan:** [202608/flake\_class\_residue.md](https://github.com/sase-org/sase--plans/blob/main/202608/flake_class_residue.md)

## Description

Epic sase-h8 reaches the exit criterion it wrote for itself and could not meet. The `clock` phase, whose bead closed `done` with zero commits after its agent stalled on a soak, is actually implemented: the stall watchdog runs off an injectable time source so its five F2 nodes assert exact episode counts instead of tolerances, and the contract-set budget guard stops depending on real elapsed wall clock. The four nodes that failed `just test-contention` at the land attempt are fixed by mechanism under the same discipline. The wait-helper gate stops missing the idiom it was built to retire, so post-epic commits cannot silently reintroduce it. Only then does sase-h8 close and sase-ct close on the measured, enforced criterion the epic promised.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.land/README.md) | [sase-h8.10](sase-h8.10.md) | 0 |

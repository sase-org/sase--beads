# Bead: sase-9v.9 — Make every sase-core bead mutation atomic against concurrent writers

[Bead Pages](../README.md) / [sase-9v](README.md) / sase-9v.9

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9v.9` · **Size:** medium
**Created:** 2026-07-26 15:32:33 UTC
**Plan:** [sase/repos/plans/202607/bead\_review\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/bead_review_hardening.md)

## Description

core_mutation_atomicity: extend with_bead_mutation_lock to all bead store mutations (not just the three claim functions), write JSONL through per-process temp files, align missing-dependency semantics between ready/blocked reads and the epic work planner, and remove the dead OperationOutcomeWire type. Implemented in the sase-core repo.

## Notes

Implemented in linked sase-core: serialized every listed bead mutation with the shared beads.db flock; made JSONL/event writes use PID+counter temp paths; treated missing epic blockers as satisfied with plan warnings; removed OperationOutcomeWire; added concurrent update+claim, unique-temp, and dangling-blocker regressions. Verified with cargo bead tests, just rust-check, and just bead-perf-smoke.

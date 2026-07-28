# Bead: sase-ak.2 — Shared tribe wait binding resolver

[Bead Pages](../README.md) / [sase-ak](README.md) / sase-ak.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.2` · **Size:** medium
**Created:** 2026-07-28 21:05:20 UTC · **Closed:** 2026-07-28 21:22:13 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

tribe-wait-binding: extract the `tribe_candidate` ordering and aggregation rules into a pure, snapshot-driven resolver in Python core that both the wait index and the TUI can call, and add a pending/bound/reserved classification the display layer can consume without touching disk.

## Notes

[2026-07-28T21:21:56Z · sase-ak.2] Implemented the pure snapshot-driven tribe wait binding resolver, re-exported it, and delegated WaitDependencyIndex.tribe_candidate to it while preserving exact TribeCandidate members for fork callers. Added coverage for strict cutoff/self exclusion, direct/effective clan enrollment, whole-generation completion, ordering, pending details, and reserved classification. Verification: focused resolver/index suite 16 passed; ruff and mypy passed; full just test 23248 passed, 7 skipped; committed-plan validation passed. just check was run and every format/lint stage passed, but its global SASE validation stopped on the epic's pre-existing missing plans-checkout target 202607/tribe_wait_reference_validation_and_display.md.

## Dependencies

- **Blocks:** [sase-ak.3](sase-ak.3.md) ✓

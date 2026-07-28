# Bead: sase-8h.3 — Truthful commits-pane status, cap visibility, and cache correctness

[Bead Pages](../README.md) / [sase-8h](README.md) / sase-8h.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8h.3` · **Size:** medium
**Created:** 2026-07-21 14:14:46 UTC
**Plan:** [202607/commits\_filter\_correctness.md](https://github.com/sase-org/sase--plans/blob/main/202607/commits_filter_correctness.md)

## Description

'Phase 3: Truthful commits-pane status, cap visibility, and cache correctness' section: make the filter bar report "N+ / capped" instead of "exact" when results were truncated, surface the active row cap in the pane, key the pane's caches and change-detection off text-normalized filter values so unchanged queries and relative windows behave correctly in long sessions, and refresh docs, help text, and PNG goldens.

## Notes

COMMIT: 54e8736ea

## Dependencies

- **Depends on:** [sase-8h.1](sase-8h.1.md) ✓
- **Depends on:** [sase-8h.2](sase-8h.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8h.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8h.3/README.md) | [sase-8h.3](sase-8h.3.md) | 1 |
| [bbugyi200.athena.sase-8h.3--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8h.3.md#member-code) | [sase-8h.3](sase-8h.3.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`54e8736`](https://github.com/sase-org/sase/commit/54e8736ea7ed487b3f600ad71939316764957b43) | fix(ace): report capped commit results truthfully (sase-8h.3) | [sase-8h.3](sase-8h.3.md) | 2026-07-21 16:17:45 |

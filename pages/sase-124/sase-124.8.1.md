# Bead: sase-124.8.1 — Correct capacity inputs and asynchronous result ordering

[Bead Pages](../README.md) / [sase-124.8](sase-124.8.md) / sase-124.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-124.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-124.land.md) · **Assignee:** `sase-124.8.1` · **Size:** medium
**Created:** 2026-09-17 17:43:30 EDT · **Closed:** 2026-09-17 18:36:05 EDT
**Plan:** [202609/finish\_agents\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agents_freshness.md)

## Description

capacity-ordering: use the canonical capacity roster including hidden and empty cases, guard all changing inputs, and keep stale-result recomputation off the UI thread with deterministic race regressions.

## Notes

[2026-09-17T22:36:05Z · sase-124.8.1] Implemented canonical capacity roster refresh for hidden, remote-display, and empty roster cases; guarded same-generation stale results; kept stale load capacity off the UI thread and scheduled coalesced recompute. Verified focused pytest for refresh/apply paths, saved audit reproducer capacity outputs, just fix, and just check (scoped escalated to full suite). epic-symbols had no entries.

## Dependencies

- **Blocks:** [sase-124.8.2](sase-124.8.2.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-124.8.3](sase-124.8.3.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.8.1/README.md) | [sase-124.8.1](sase-124.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f1616c5`](https://github.com/sase-org/sase/commit/f1616c505e3581cea78f3ac9c21efb4361312a79) | fix(tui): correct agents capacity ordering | [sase-124.8.1](sase-124.8.1.md) | 2026-09-17 18:37:58 EDT |

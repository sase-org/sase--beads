# Bead: sase-u.4 — Phase 4 — j/k input coalescing & universal detail-panel debounce

[Bead Pages](../README.md) / [sase-u](README.md) / sase-u.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-u.4`
**Created:** 2026-04-26 07:23:48 UTC · **Closed:** 2026-04-26 08:17:43 UTC
**Plan:** [202604/instant\_jk\_navigation.md](https://github.com/sase-org/sase--plans/blob/main/202604/instant_jk_navigation.md)

## Description

Generalize 150ms debouncer into tab-agnostic DetailPanelDebouncer; coalesce j/k bursts so cursor highlight is immediate but expensive follow-up only runs on quiesce. Target: key-to-highlight p95 < 16ms.

## Notes

COMMIT: 2b946c3a

## Dependencies

- **Depends on:** [sase-u.3](sase-u.3.md) ✓
- **Blocks:** [sase-u.5](sase-u.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e44715f`](https://github.com/sase-org/sase/commit/e44715f2c8cd921c09af784ee0225ae5b837326d) | feat(ace): tab-agnostic detail-panel debouncer for j/k navigation (sase-u.4) | [sase-u.4](sase-u.4.md) | 2026-04-26 08:17:47 |

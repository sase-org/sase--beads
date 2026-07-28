# Bead: sase-u.5 — Phase 5 — Event-driven background refresh, pausable during input bursts

[Bead Pages](../README.md) / [sase-u](README.md) / sase-u.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-u.5`
**Created:** 2026-04-26 07:23:58 UTC · **Closed:** 2026-04-26 08:31:29 UTC
**Plan:** [202604/instant\_jk\_navigation.md](https://github.com/sase-org/sase--plans/blob/main/202604/instant_jk_navigation.md)

## Description

Replace 10s polling with inotify watcher (with polling fallback). Add 'user is navigating' gate that defers reconciliation when j/k fired within last 250ms. Audit ChangeSpecs and Axe pollers similarly.

## Notes

COMMIT: 48f0a552

## Dependencies

- **Depends on:** [sase-u.4](sase-u.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3e8a9f9`](https://github.com/sase-org/sase/commit/3e8a9f97c0b932faffee5ea06b10f1a448c994ef) | feat(ace): event-driven artifact refresh with j/k nav gate (sase-u.5) | [sase-u.5](sase-u.5.md) | 2026-04-26 08:31:33 |

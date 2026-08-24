# Bead: sase-su.4 — Launch Control relaunch prompt after a manual disable

[Bead Pages](../README.md) / [sase-su](README.md) / sase-su.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ce](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ce.md) · **Assignee:** `sase-su.4` · **Size:** medium
**Created:** 2026-08-24 10:29:14 EDT · **Closed:** 2026-08-24 13:25:06 EDT
**Plan:** [202608/provider\_drain.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_drain.md)

## Description

ace: after a manual hard disable in the Models panel, offer a single-keypress relaunch chooser and submit the drain as a durable tracked proc.

## Notes

[2026-08-24T16:58:42Z · sase-su.4] PROPOSED FOLLOW-UP: Repair home memory init drift — just check fails in SASE validation because init memory --check reports generated home memory/provider-shim drift and unreferenced ~/.local/share/chezmoi/home/sase/memory/obsidian.md.

[2026-08-24T17:25:06Z · sase-su.4] Implemented ACE provider-drain prompt and durable relaunch submission after manual hard provider disables. Verified focused modal/durable/inventory tests, visual snapshot update and compare, stale Symvision whitelist cleanup, proc-env adapter compatibility, just test-scoped full lane passed 36694/13 skipped; just check reaches SASE validation and is blocked only by home memory init drift recorded as a proposed follow-up.

## Dependencies

- **Depends on:** [sase-su.2](sase-su.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-su.5](sase-su.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-su.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-su.4/README.md) | [sase-su.4](sase-su.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54ede7f`](https://github.com/sase-org/sase/commit/54ede7fa5d078fcdd51ace041b04e5bcfdf530b5) | feat(ace): prompt provider drain relaunch after disable | [sase-su.4](sase-su.4.md) | 2026-08-24 13:27:57 EDT |

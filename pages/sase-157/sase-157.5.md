# Bead: sase-157.5 — Fix the detached handoff started-path mismatch

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.5` · **Size:** medium
**Created:** 2026-09-21 06:25:48 EDT · **Closed:** 2026-09-21 10:59:51 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

sudo-started-path: stop comparing a caller-supplied --started-path against one derived from a canonicalized --detach-dir, and correct the remaining sudo_runner cwd and sudo-order path expectations.

## Notes

[2026-09-21T13:55:58Z · sase-157.5] PROPOSED FOLLOW-UP: macOS CI leg never reaches tests — Read pinned toolchain step passes channel = "stable" (GNU grep/sed-isms fail on macOS BSD tools); blocks sase-157.9 from going green

[2026-09-21T14:59:51Z · sase-157.5--1] Started-path fix verified. Linux: full gate green, 46/46 sudo_runner incl symlinked TMPDIR; fmt clean. macOS: full check.sh run shows only failure is git_object_sharing relative_alternates (/private/tmp vs /tmp, sibling scope, untouched); focused sudo_runner suite 46/46 x6 runs. Fixed 2 mac-only storm flakes in same file: hold-pipe test (printf-first stub, portable setsid probe, timeout 0.2->2s, bound 3->6s) and waiting-worker argv wait (deadline 1->10s). Mac checkout restored to clean master, mac /tmp artifacts removed.

## Dependencies

- **Depends on:** [sase-157.4](sase-157.4.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.9](sase-157.9.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-157.5.md) | [sase-157.5](sase-157.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3e346b0`](https://github.com/sase-org/sase-core/commit/3e346b045ca0f3832f92ff8265f1d5d4ac5215e7) | fix(sase-gateway): stabilize sudo\_runner hold-pipe stub and waiting-worker timing under parallel load | [sase-157.5](sase-157.5.md) | 2026-09-21 11:02:53 EDT |

# Bead: sase-1c1.7 — Fix header half-page scroll and files Ctrl-J settle races

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.7` · **Size:** medium
**Created:** 2026-09-28 07:09:32 EDT · **Closed:** 2026-09-28 09:47:23 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

tui-scroll-settle: root-cause the asynchronous pin settle behind the header half-page scroll test (sase-1b8) and the files deck Ctrl-J timeout (sase-1a7), and fix them without blindly longer waits.

## Notes

[2026-09-28T13:47:23Z · sase-1c1.7--1] Verified header pin settling and Files Ctrl-J across 20 xdist repetitions. sase tool run check passed formatting, lint, SASE validation, and committed-plan stages, then timed out at 45 minutes with test (scoped) incomplete and no test failure output.

## Dependencies

- **Blocks:** [sase-1c1.12](sase-1c1.12.md) ◐ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.7.md) | [sase-1c1.7](sase-1c1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b536e0c`](https://github.com/sase-org/sase/commit/b536e0c26771143023a9f784bba8e5cc78ae0790) | fix(ace): settle header and files deck scrolling | [sase-1c1.7](sase-1c1.7.md) | 2026-09-28 09:49:03 EDT |

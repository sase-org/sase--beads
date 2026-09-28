# Bead: sase-1c1.7 — Fix header half-page scroll and files Ctrl-J settle races

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.7` · **Size:** medium
**Created:** 2026-09-28 07:09:32 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

tui-scroll-settle: root-cause the asynchronous pin settle behind the header half-page scroll test (sase-1b8) and the files deck Ctrl-J timeout (sase-1a7), and fix them without blindly longer waits.

## Dependencies

- **Blocks:** [sase-1c1.12](sase-1c1.12.md) ◐ · ⧖ 2026-09-28
- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.7.md) | [sase-1c1.7](sase-1c1.7.md) | 0 |

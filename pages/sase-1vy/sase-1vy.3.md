# Bead: sase-1vy.3 — Axe j/k benchmark must not capture Agents-tab samples under load (sase-199)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.3` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

bench-integrity: fix sase-199. Read sase-199 and all of its notes first. The Axe j/k bench collects samples from tabs other than the measured one under load (4 corroborations). Scope the sample window to the measured tab so bench results stay meaningful. Cover with a regression test that fails on the old cross-tab capture. Run sase tool run check, then close sase-199 and the phase bead.

## Dependencies

- **Depends on:** [sase-1vy.2](sase-1vy.2.md) ◐ · ⧖ 2026-11-28
- **Blocks:** [sase-1vy.4](sase-1vy.4.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vy.3/README.md) | [sase-1vy.3](sase-1vy.3.md) | 0 |

# Bead: sase-1vy.5 — Tool-admission overlap flake: rule out a real limit violation (sase-1vw)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.5` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

admission-overlap-flake: fix sase-1vw. Read sase-1vw and all of its notes first (related sase-1ve tracks a different node in the same module). test_limit_two_with_four_runs_never_overlaps_more_than_two failed once under host load with no admission change in the finding diff, then passed 5/5 isolated plus a green whole-module run. Determine whether the overlap measurement needs a semantic wait or the failure is a real admission-limit violation with more than two concurrent runs at limit two; fix whichever it is. Do not close on a single green rerun. Run sase tool run check, then close sase-1vw and the phase bead.

## Dependencies

- **Depends on:** [sase-1vy.4](sase-1vy.4.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vy.5/README.md) | [sase-1vy.5](sase-1vy.5.md) | 0 |

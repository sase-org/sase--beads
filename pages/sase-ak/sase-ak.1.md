# Bead: sase-ak.1 — Reject reserved tribe references in wait and fork targets

[Bead Pages](../README.md) / [sase-ak](README.md) / sase-ak.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.1` · **Size:** small
**Created:** 2026-07-28 21:05:09 UTC · **Closed:** 2026-07-28 21:16:57 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

reserved-tribe-guard: add a canonical reserved-tribe concept to core and reject `@default` (and any other reserved pseudo-tribe) wherever a tribe reference is used as a `%wait` or `#fork` target, so the launch fails with a clear message instead of parking forever.

## Dependencies

- **Blocks:** [sase-ak.4](sase-ak.4.md) ◎

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ak.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.1/README.md) | [sase-ak.1](sase-ak.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d67de4c`](https://github.com/sase-org/sase/commit/d67de4caf9530ff1a4912ffa4ecf2727a50d35df) | fix(tribes): reject reserved tribe references in wait and fork targets | [sase-ak.1](sase-ak.1.md) | 2026-07-28 21:17:58 |

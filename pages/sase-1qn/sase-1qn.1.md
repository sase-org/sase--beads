# Bead: sase-1qn.1 — Stop --epic-symbol rows from outliving their bead (sase-o7)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.1` · **Size:** large
**Created:** 2026-11-01 14:34:48 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

epic-symbol-lifecycle: find why Justfile --epic-symbol rows keyed to a closed bead still reach master after the 8bea2e8414 close guard (2026-10-30 recurrences for sase-1pj.4.1, sase-1pj.5.1.3, sase-1pj.5.1.4), and close that gap at the lifecycle point that actually creates it, so unrelated agents stop discovering stale rows at the symvision lint gate. Keep the closed-bead symvision refusal and the epic-whitelist policy. Add regression coverage for the reproduced path.

## Notes

[2026-11-01T19:48:59Z · sase-1qn.1] INVESTIGATION: At sase 078e3da1d6, the three October 30 examples do not show stale rows newly reaching master after close. Cleanup 0060c20fd7 (09:10:20Z) precedes sase-1pj.4.1 close (09:15:20Z); f7eb80c7a8 (09:48:21Z) precedes sase-1pj.5.1.3 close (09:53:33Z); 7da649b562 (16:19:49Z) precedes sase-1pj.5.1.4 close (16:57:24Z). The .4 history explicitly records an upstream-row close refusal before cleanup publication. ToolRun 3ca0ba01382eb58f81f4b5063766ebe1 started at 16:59:15Z for 16a--1 from older HEAD db37d68096 (14:14:05Z), with Justfile untouched. That HEAD is an ancestor of 7da649b562 and retains all eight obsolete rows. This proves a stale observer checkout against live closed-bead status, not a broken contemporary master. The approved parent scope remains sase-o7 only. Prepared a medium tale for an early evidence-based stale-checkout verification refusal and regression coverage, preserving the existing close guard and Symvision policy. No production code changed; implementation and phase closure remain for the plan coder.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.1.md) | [sase-1qn.1](sase-1qn.1.md) | 0 |

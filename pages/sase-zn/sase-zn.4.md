# Bead: sase-zn.4 — Bound retained child-process output in the session proc reporter

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.4` · **Size:** small
**Created:** 2026-09-11 12:20:21 EDT · **Closed:** 2026-09-11 16:57:55 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

stream-bound: cap the unbounded in-memory output list in _stream_subprocess and stop mirroring the whole stream into operation-request.json records that reached 40 MB each.

## Notes

[2026-09-11T20:57:22Z · sase-zn.4] PROPOSED FOLLOW-UP: Bound agent.cleanup operation-request.json payloads — 633 files on this host are 1–40 MB because they serialize the full agents_with_children corpus (action/cleanup_plan/identity), not child-process stdout; stream-bound does not shrink them, and ~/.sase/procs/runtime still has no retention policy for those sidecars.

[2026-09-11T20:57:55Z · sase-zn.4] Bounded _stream_subprocess CompletedProcess.stdout to a 2 MiB head+tail OutputCapture (SESSION_PROC_MAX_OUTPUT_BYTES); JSON init-check uses retain=full. Verified: under-cap stdout is byte-identical, over-cap output is marked and bounded while on_line still sees every line, retain=full bypasses the cap, init-check still passes retain=full, and tests/ace/tui/test_session_proc_reporter.py plus init-flow tests pass (16+3). ruff/mypy/fmt clean. Callers audited: uv/command/dev runners keep default bounded retention (parse tails or small git output); 40 MB operation-request.json files are agent.cleanup agents_with_children, recorded as PROPOSED FOLLOW-UP. epic-symbols: none.

## Dependencies

- **Blocks:** [sase-zn.7](sase-zn.7.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.4/README.md) | [sase-zn.4](sase-zn.4.md) | 0 |

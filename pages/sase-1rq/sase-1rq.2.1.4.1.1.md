# Bead: sase-1rq.2.1.4.1.1 — Capture resource and progress evidence for the runner shutdown

[Bead Pages](../README.md) / [sase-1rq.2.1.4.1](sase-1rq.2.1.4.1.md) / sase-1rq.2.1.4.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.md) · **Assignee:** `sase-1rq.2.1.4.1.1` · **Size:** medium
**Created:** 2026-11-07 11:04:38 EST
**Plan:** [202611/contention\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/contention_repair.md)

## Description

evidence: Add bounded, outcome-neutral contention diagnostics and obtain a monitored reproduction that distinguishes collection pressure, runtime leaks, disk exhaustion, and process termination. Publish the measurements and the narrowest supported failure mechanism for the survival phase.

## Notes

[2026-11-07T17:20:14Z · sase-1rq.2.1.4.1.1] EVIDENCE (preliminary, before the hosted diagnostic run): (1) Hosted signature is identical in every visible Telemetry contention-test job since 2026-10-19 (>=35 runs, never once completed), e.g. job 118110548551/run 39264991134 (2026-10-19, py3.12.15), 128332909537/run 42347892210, 128421280632/run 42377692789 (SHA 0ba9cfc9f1): `contention soak: 1 repeat(s), 26 workers` at start, 17-30 min of silence, then 1-5 `Received SIGTERM - agent was killed`, (run 42377692789) `Recipe test-contention was terminated on line 766 by signal 15` 0.15 s later, then `##[error]The runner has received a shutdown signal`, then 25 `Terminate orphan process ... (python)`. Zero pytest stdout, not even the session header. (2) pytest 9.x terminal reporter flushes piped stdout on every test logstart/logreport, and xdist schedules no test until all workers have collected; so zero output means no test ever reported: every hosted death happened during 26-way worker collection. (3) `Received SIGTERM - agent was killed` is src/sase/axe/runner_signals.py, installed soft=True AT IMPORT by src/sase/axe/run_agent_runner.py:87; xdist workers that imported it during collection print that line and IGNORE SIGTERM, which is why 25 workers survived and were orphan-killed. The SIGTERM was broad (just recipe child died of signal 15 at the same instant, before the runner logged its own shutdown): a whole-job/runner termination, sender unknown. (4) Local (athena, py3.14.7, pytest 9.1.1, xdist 3.8.0, SHA 5692321a2e): one process collecting the default selection (-m "not slow and not visual", visual paths ignored) = 60,493 items, 84.6 s wall, 53.6 s user + 3.2 s sys, max RSS 1036 MB. 26 workers each collect everything: ~25 CPU-min on 2 pinned CPUs and ~26 GB worker RSS vs a 16 GB ubuntu-latest runner. Local 26-worker subset (3 files, 32 tests) already used 4.4 GB worker RSS. Provisional narrowest mechanism: memory exhaustion during 26-way collection on the hosted runner, ended by a broad SIGTERM of unproven origin. Runtime leak excluded for hosted runs (no test ran); disk unmeasured but not implicated during collection. Sender and memory curve still unknown pending the diagnostic run.

[2026-11-07T17:20:19Z · sase-1rq.2.1.4.1.1] PROPOSED FOLLOW-UP: run_agent_runner installs a soft SIGTERM handler at import time - src/sase/axe/run_agent_runner.py:87 calls install_sigterm_handler("agent", soft=True) as a module side effect, so any process that merely imports the module (every pytest worker that collects a test importing it) prints "Received SIGTERM - agent was killed" and ignores SIGTERM afterwards; in Telemetry this left 25 xdist workers alive after the job SIGTERM (runner orphan cleanup had to kill them) and it can mask SIGTERM-based teardown in tests. Move installation into the runner entry point.

## Dependencies

- **Blocks:** [sase-1rq.2.1.4.1.2](sase-1rq.2.1.4.1.2.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.4.1.1.md) | [sase-1rq.2.1.4.1.1](sase-1rq.2.1.4.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f97019e`](https://github.com/sase-org/sase/commit/f97019e7e8a4f600d273462f1ebe83de41f30837) | feat(test-contention): sample soak resources and signal senders | [sase-1rq.2.1.4.1.1](sase-1rq.2.1.4.1.1.md) | 2026-11-07 12:22:13 EST |

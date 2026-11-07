# Bead: sase-1rq.2.1.4 — Make the contention-test lane survive and pass

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.4` · **Size:** large
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

contention: CI Telemetry's contention-test job (SASE_CONTENTION_REPEAT=1 just test-contention, 26 workers on 2 pinned CPUs) prints nothing for about 20 minutes. Then the runner gets a shutdown signal, on both the 06:54 and 13:48 UTC runs on 2026-11-07. The lane has never produced a tally in CI. Find out why the runner dies (memory or disk exhaustion is the lead) and fix it without changing the width, repeat count, CPU pinning, or timeout. Then make the single repeat pass: root-cause each failure under contention, or quarantine proven flakes.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.4/README.md) | [sase-1rq.2.1.4](sase-1rq.2.1.4.md) | 0 |

# Bead: sase-1rq.2.1.2 — Stop the coverage-contexts lane crashing on global disk patches

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.2` · **Size:** medium
**Created:** 2026-11-07 10:24:47 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

coverage-contexts: CI Telemetry's coverage-contexts job dies in a pytest-xdist INTERNALERROR. test_inflight_handler_does_no_synchronous_disk_or_proc_store_work patches os.stat and pathlib.Path methods globally with a raising stub. Coverage's ctrace tracer then calls os.path.exists while the patch is active and hits the assertion inside the tracer. Scope that guard so it only sees the code under test. Audit the other tests that globally patch os, os.path, or pathlib with raising stubs for the same hazard, and prove the cov-contexts lane passes on the affected modules.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.2/README.md) | [sase-1rq.2.1.2](sase-1rq.2.1.2.md) | 0 |

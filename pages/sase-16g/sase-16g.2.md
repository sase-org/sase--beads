# Bead: sase-16g.2 — Restart is a confirmed transition

[Bead Pages](../README.md) / [sase-16g](README.md) / sase-16g.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pe.md) · **Assignee:** `sase-16g.2` · **Size:** medium
**Created:** 2026-09-22 12:59:07 EDT · **Closed:** 2026-09-22 14:23:56 EDT
**Plan:** [202609/services\_p0\_supervision.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_p0_supervision.md)

## Description

restartgen: move the sase-core revision pin, rebuild start and restart on the new request generation, have the host consume requests and record the pid it produced, and make the CLI wait for that generation, print old pid to new pid, and fail honestly.

## Notes

[2026-09-22T18:03:03Z · sase-16g.2] PROPOSED FOLLOW-UP: just check symvision gate is red on master for agent_env_refusal_reason in src/sase/service/platform.py (unused public, only in-file use at line 272 plus tests); pre-existing from closed phase sase-16g.6, verified by running just _lint-symvision on clean HEAD

[2026-09-22T18:20:38Z · sase-16g.2] PROPOSED FOLLOW-UP: test_preview_modal_resize_recomputes_geometry fails on clean HEAD (expects 160x60, gets 100x30); environment-dependent TUI geometry, unrelated to restartgen

[2026-09-22T18:21:20Z · sase-16g.2] PROPOSED FOLLOW-UP: test_test_shards measured-count gate fails on clean HEAD (file count drifted 23% past the 20% gate; run just refresh-shard-timings); pre-existing, unrelated to restartgen

[2026-09-22T18:23:56Z · sase-16g.2] restartgen done: pin ratcheted to 7a2ff34; request/complete facade in state.py with request round-tripped through status.py; start/restart issue one request mutation with generation and wait helper; host consumes requests (restarted/started/already_running/not_desired/unknown_proc/failed) before the launch loop; CLI waits with default max(15, stop_timeout+10), prints pid OLD -> pid NEW, exits 1 on timeout/not-desired/failed/host-down, -n/--no-wait and -t/--timeout on proc and scheduler paths; update reports restarted only on confirmation else unconfirmed yellow warning; docs and completion snapshot updated. Verified: 100 passed across 8 affected test files, ruff/mypy/keep-sorted/fmt clean, no epic-symbols left.

## Dependencies

- **Depends on:** [sase-16g.1](sase-16g.1.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16g.3](sase-16g.3.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16g.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.2/README.md) | [sase-16g.2](sase-16g.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`00106bb`](https://github.com/sase-org/sase/commit/00106bbef8f03681669461e543f614afd8e43f0c) | feat(service): restarts are confirmed generation transitions with honest CLI outcomes | [sase-16g.2](sase-16g.2.md) | 2026-09-22 14:26:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16g.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.2/README.md

<!-- sase:referenced-by:end -->

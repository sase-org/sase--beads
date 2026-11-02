# Bead: sase-1qt.3 — Fix the sase-core sudo\_runner ETXTBSY fixture flake (sase-15h)

[Bead Pages](../README.md) / [sase-1qt](README.md) / sase-1qt.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.land.md) · **Assignee:** `sase-1qt.3` · **Size:** medium
**Created:** 2026-11-01 18:08:20 EST · **Closed:** 2026-11-01 18:37:52 EST
**Plan:** [202611/task\_backlog\_epic\_5.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_5.md)

## Description

core-sudo-runner-etxtbsy: in sase-core, sase_gateway sudo_runner tests intermittently fail with ETXTBSY (os error 26) when exec'ing fixture scripts under the parallel core check (+7, latest 2026-10-31). Confirm the fork-inherited write-fd race on freshly written fixture executables and fix the fixture so no test can exec a script while any process still holds it open for writing, keeping every sudo_runner assertion.

## Notes

[2026-11-01T23:37:34Z · sase-1qt.3] TASK RESOLVED: sase-15h — evidence: base sase-core e60f3e16 on athena. Mechanism confirmed live two ways: (1) new deterministic test holds a script open for writing across a forked sleep child and the exec fails with ETXTBSY os error 26; (2) a parallel-suite run produced a live ETXTBSY on a script whose writer had already closed (foreign inheritor) — the exact fleet flake shape. Fix: publish_executable (write-tmp + chmod + atomic rename under a process-wide spawn lock) for every sudo_runner script writer — Fixture::new fake-sudo/fake-executor, write_executable (waiting-worker + 6 worker.rs sites), 2 direct worker.rs writes converted to the helper; per-spawn-attempt lock inside retry_on_etxtbsy (cfg(test)-only, never across waits/sleeps); bounded ETXTBSY-only retry (250x2ms) at all 5 spawn sites as documented backstop. No assertion changed; dispatch relative.txt + manifest/marker JSON are never execd data files, intentionally unchanged.

[2026-11-01T23:37:43Z · sase-1qt.3] Verification: 56/56 sudo_runner tests pass (53 existing + 3 new etxtbsy regression tests); 15/15 parallel stress iterations green; sase tool run check in sase-core verdict pass (run 570abe2c0c68d1cc1d33a5c51c31a32b). Limits: an intermediate whole-run lock design broke 2 timing tests (75ms stop-file, 2s live-log poll) and was replaced with per-spawn-attempt guards — both pass since. No memory edits per keep_five_seeds. No wire/binding changes, so no sase-core pin move is needed from this phase. sase-core tree left uncommitted for host finalizers (agents never commit). No PROPOSED FOLLOW-UP: adjacent sase-15e/sase-15f are separately owned beads, untouched.

[2026-11-01T23:37:52Z · sase-1qt.3] sudo_runner ETXTBSY fixture race fixed in sase-core: atomic script publication under a spawn lock + per-spawn guards + bounded ETXTBSY retry backstop at all 5 spawn sites; every assertion kept. Verified: 56/56 focused pass, 15/15 stress iterations green, sase tool run check verdict pass (570abe2c). No epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qt.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qt.3/README.md) | [sase-1qt.3](sase-1qt.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b0a63dc`](https://github.com/sase-org/sase-core/commit/b0a63dc3a26741a9194d716ee4764b47a4ab6bae) | fix(sudo-runner): serialize fixture script publication against spawns with ETXTBSY retry backstop | [sase-1qt.3](sase-1qt.3.md) | 2026-11-01 18:38:44 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qt.3][1] | check full description notes and design | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qt.3/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1lh.7.5.4.3.3.4.3 — Observe the compatible core and guarded sase 0.18.0 publication

[Bead Pages](../README.md) / [sase-1lh.7.5.4.3.3.4](sase-1lh.7.5.4.3.3.4.md) / sase-1lh.7.5.4.3.3.4.3

**Status:** ✓ closed · **Resolution:** canceled · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.5.4.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.land.md) · **Assignee:** `sase-1lh.7.5.4.3.3.4.3` · **Size:** small
**Created:** 2026-10-17 17:10:45 EDT · **Closed:** 2026-10-17 21:34:20 EDT
**Plan:** [202610/finish\_release\_gate\_fixtures.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_release_gate_fixtures.md)

## Description

watch: verify the committed fixes, choose a containing core release target, and run one self-closing release watch whose monitor has no follow-up and always settles.

## Notes

[2026-10-17T23:16:40Z · sase-1lh.7.5.4.3.3.4.3] Watch inputs and preflight: FIXED_SHA=933970ce72a5b5328499e80751a491c857bfc221 (current origin/master); CORE=0.42.0 from open core PR #331, whose branch contains pinned core fix dd56b94a8ad9fdca541d16cb5b6f85a2b45e55af. Sase #299 remains open, sase 0.18.0 is absent from GitHub releases/PyPI, and core PyPI remains 0.41.0. Preflight passed exit 0 with parsed state: 2026-10-17T23:16:20Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:None:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core. Full preflight: PYTHONUNBUFFERED=1 NO_COLOR=1 GH_FORCE_TTY=0 tools/release_watch --repo sase-org/sase --version 0.18.0 --fixed-sha 933970ce72a5b5328499e80751a491c857bfc221 --await-core-version 0.42.0 --once --dry-run --close-bead sase-1lh.7.5.4.3.3.4.3. Starting exactly one no-successor monitor with: PYTHONUNBUFFERED=1 NO_COLOR=1 GH_FORCE_TTY=0 timeout -k 10m 750m tools/release_watch --repo sase-org/sase --version 0.18.0 --fixed-sha 933970ce72a5b5328499e80751a491c857bfc221 --await-core-version 0.42.0 --deadline 12h --close-bead sase-1lh.7.5.4.3.3.4.3; rc=$?; echo "RELEASE_WATCH_EXIT=$rc"; sleep 120; sase bead close sase-1lh.7.5.4.3.3.4.3 -R canceled -r "release not confirmed: watcher exit $rc left the bead open" || true; exit 0. PROPOSED FOLLOW-UP: repair the remaining macOS openat variadic mode arguments in core before 0.42.0 can pass CI; PR #331 job 117510033363 fails at fs.rs:191 and :393 because libc::mode_t is u16 there, which Rust rejects for the variadic openat mode argument. The pending PR branch includes the phase 4.1 fix but this separate compiler error remains.

[2026-10-18T01:34:20Z · bryanbugyi34@gmail.com] RELEASE NOT CONFIRMED: MASTER_GATE_RED

Evidence:
- repo: sase-org/sase
- version: 0.18.0
- fixed SHA: 933970ce72a5b5328499e80751a491c857bfc221
- await-core-version: 0.42.0
- verdict: MASTER_GATE_RED (exit 17)
- detail: no green Master Gate at HEAD 933970ce72a5b5328499e80751a491c857bfc221 for 124.7 minutes (budget 120): run 39077497974 https://github.com/sase-org/sase/actions/runs/39077497974 conclusion=failure failed_jobs=test (8)
- actions: dispatched:master_gate_rerun, dispatched:full_ci
- state: 2026-10-17T23:17:48Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:None:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:23:42Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:None:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:29:38Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core,dispatched:master_gate_rerun
- state: 2026-10-17T23:35:32Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:None:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:41:25Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:47:20Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:53:18Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-17T23:59:14Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:05:10Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:11:06Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:17:02Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:22:59Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:28:55Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:34:50Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:40:44Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:46:42Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:52:40Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T00:58:35Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T01:04:32Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T01:10:30Z stage=watch pypi=absent release_pr=#299:open full_ci=none master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core,dispatched:full_ci
- state: 2026-10-18T01:16:26Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T01:22:23Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T01:28:19Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=awaiting_core
- state: 2026-10-18T01:34:18Z stage=watch pypi=absent release_pr=#299:open full_ci=in_flight:1 master_gate=39077497974:failure:933970ce72a5 publish=39077813839:success core_pypi=0.41.0@2026-10-17T13:03:55Z action=verdict:MASTER_GATE_RED
- PyPI watched version: absent
- sase-core-rs PyPI: 0.41.0 uploaded 2026-10-17T13:03:55Z
- ci_watch release_reason: gating_workflow_red
- release PR: #299 https://github.com/sase-org/sase/pull/299 state=OPEN merged_at=not-merged merge_state=UNSTABLE head=d3f2ba36c7580e1da8ba9a9eaf90016e1da8b1fc head_created_at=2026-10-17T23:11:07Z
  rollup: Conventional PR title=success, ace-page-group-isolation=skipped, build-core / build-core=skipped, docs-build=skipped, lint=skipped, perf-floors=skipped, release-core-floor-smoke=failure, test=skipped, tutorial-tests=skipped, visual-test=skipped
- master HEAD: 933970ce72a5b5328499e80751a491c857bfc221
- Master Gate runs:
  - id=39077497974 url=https://github.com/sase-org/sase/actions/runs/39077497974 sha=933970ce72a5b5328499e80751a491c857bfc221 status=completed conclusion=failure created_at=2026-10-17T23:03:06Z updated_at=2026-10-17T23:40:40Z jobs=[test (8)=failure,test (7)=success,docs=success,core-wheel=success,test (1)=success,test (6)=success,test (2)=success,test (4)=success,test (3)=success,test (5)=success,lint=success]
- Full CI runs:
  - id=39085508146 url=https://github.com/sase-org/sase/actions/runs/39085508146 sha=933970ce72a5b5328499e80751a491c857bfc221 status=in_progress conclusion=in-flight created_at=2026-10-18T01:10:30Z updated_at=2026-10-18T01:22:58Z jobs=[not fetched]
- Publish runs:
  - id=39077813839 url=https://github.com/sase-org/sase/actions/runs/39077813839 sha=933970ce72a5b5328499e80751a491c857bfc221 status=completed conclusion=success created_at=2026-10-17T23:07:55Z updated_at=2026-10-17T23:11:12Z jobs=[release=success,sync-release-metadata=success,build=skipped,install-smoke-core-floor=skipped,publish=skipped,install-smoke=skipped]
  - id=39067450380 url=https://github.com/sase-org/sase/actions/runs/39067450380 sha=2dd7fe7f8e204d874166ec222199383b81a58c16 status=completed conclusion=success created_at=2026-10-17T20:36:45Z updated_at=2026-10-17T20:40:24Z jobs=[release=success,sync-release-metadata=success,install-smoke-core-floor=skipped,install-smoke=skipped,publish=skipped,build=skipped]
  - id=39045714836 url=https://github.com/sase-org/sase/actions/runs/39045714836 sha=a80f2891e8cd4bdbf783d9ca54419434974159c5 status=completed conclusion=succe

… and 24485 more characters

## Dependencies

- **Depends on:** [sase-1lh.7.5.4.3.3.4.2](sase-1lh.7.5.4.3.3.4.2.md) ✓ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.3.md) | [sase-1lh.7.5.4.3.3.4.3](sase-1lh.7.5.4.3.3.4.3.md) | 0 |

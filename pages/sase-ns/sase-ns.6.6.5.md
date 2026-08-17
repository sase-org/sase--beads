# Bead: sase-ns.6.6.5 — Deflake headless epic approval against an inflight launch (sase-nz)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.5` · **Size:** large
**Created:** 2026-08-17 04:03:11 EDT · **Closed:** 2026-08-17 04:53:05 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

approval_anchor: root-cause and fix tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor failing intermittently under the full parallel lane, without weakening the inflight-launch-holds-anchor assertion.

## Notes

[2026-08-17T08:52:08Z · sase-ns.6.6.5] PROPOSED FOLLOW-UP: retire sase-nz's pre-fix flake evidence — once this phase's fix
commit lands, append to tests/reproducible_flake_baseline.txt a comment naming bead
sase-nz and that commit, then
`# fixed-at: <commit UTC timestamp> tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor`
(12 pre-fix records, last 2026-08-17T01:37:59Z), and confirm
`just selection-health --fail-on-new-flake` no longer names the node.

[2026-08-17T08:52:25Z · sase-ns.6.6.5] PROPOSED FOLLOW-UP: tests/test_sdd_git_contention.py still forks a multi-threaded xdist worker in three places (_acquire_epic_plan_launch_lock, _hold_epic_plan_launch_lock and their three call sites) with the same 2.0s/5.0s/2.0s bounds. None of those nodes is a reported flake today, but they carry the same fork hazard this phase fixed, and the in-process lock-holder seam added here (_foreign_epic_launch_lock_holder in tests/test_plan_approval_actions.py) is directly reusable for them.

[2026-08-17T08:52:42Z · sase-ns.6.6.5] PROPOSED FOLLOW-UP: in-progress epic sase-j7's process-global state leak detector (tests/_global_state_leak_detector.py) fingerprints module globals, env, and caches, but does not instrument live interpreter thread count at fork time. This node's failure mode was a fork-inherited flock held by a co-resident execnet receiver thread, not a leaked module global — 'how many interpreter threads does this worker have, and who left them' is an adjacent gap sase-j7's detector does not cover.

[2026-08-17T08:53:05Z · sase-ns.6.6.5] Verified: tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor
now holds the epic plan launch lock in-process via a new _foreign_epic_launch_lock_holder
context manager (flock LOCK_EX|LOCK_NB on _epic_plan_launch_lock_path(anchor), with a
self-check that a second open() on the same path is refused with BlockingIOError) instead
of forking a subprocess from the multi-threaded xdist worker. The
inflight-launch-holds-anchor assertion is unchanged: the four patches
(resolve_epic_launch_project, get_workspace_directory, resolve_beads_location with its
side_effect=AssertionError("contended preflight must not materialize the sidecar"),
start_epic_launch_monitor) are byte-identical, start_launch.assert_called_once() and the
mon-contended monitor-id assertion both survive. The one dropped assertion is
`process.exitcode == 0`, which asserted the harness holder subprocess exited cleanly (a
property of the deleted fork-based test scaffold) rather than any property of the code
under test, so dropping it does not weaken coverage.

Verification run this session: just install; whole-file pytest
tests/test_plan_approval_actions.py -q — 22/22 passed; xdist parallel run
(-n 2 --dist=loadfile) of tests/test_plan_approval_actions.py +
tests/test_sdd_git_contention.py — 41 passed, and the multi-threaded-fork
DeprecationWarning now names only the 4 test_sdd_git_contention.py nodes, zero from
test_plan_approval_actions.py; SASE_CONTENTION_REPEAT=4 just test-contention -- \
tests/test_plan_approval_actions.py — 0 node(s) failed across 4 repeat(s); just check —
green (all lint gates + scoped test lane). just check-full started via sase monitor for
full-lane evidence; its follow-up will append the result as a separate note.

Per the plan, the flake baseline gate stays red on this node until a follow-up appends a
`# fixed-at:` entry naming this phase's landed commit (recorded as a PROPOSED FOLLOW-UP
note above). No production source file changed; scope was exactly
tests/test_plan_approval_actions.py as specified.

[2026-08-17T08:53:22Z · sase-ns.6.6.5] no-op recheck

## Dependencies

- **Depends on:** [sase-ns.6.6.1](sase-ns.6.6.1.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.6.5.md) | [sase-ns.6.6.5](sase-ns.6.6.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b6246f1`](https://github.com/sase-org/sase/commit/b6246f1cfb8b1d4d9c2d524efab7c4082ba2ee93) | test: deflake headless epic approval against an in-flight launch | [sase-ns.6.6.5](sase-ns.6.6.5.md) | 2026-08-17 04:54:01 EDT |

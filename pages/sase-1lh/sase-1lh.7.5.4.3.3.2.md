# Bead: sase-1lh.7.5.4.3.3.2 — Fix the intermittent tutorial gate and any other current gate red

[Bead Pages](../README.md) / [sase-1lh.7.5.4.3.3](sase-1lh.7.5.4.3.3.md) / sase-1lh.7.5.4.3.3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.113](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.113.md) · **Assignee:** `sase-1lh.7.5.4.3.3.2` · **Size:** medium
**Created:** 2026-10-17 14:27:20 EDT · **Closed:** 2026-10-17 14:48:29 EDT
**Plan:** [202610/green\_gates\_ship\_0\_18\_0.md](https://github.com/sase-org/sase--plans/blob/main/202610/green_gates_ship_0_18_0.md)

## Description

ci-reds: root-cause and fix the intermittent "no agents appeared after sase run" tutorial failure, make that failure self-diagnosing, and fix any other deterministic Master Gate or Full CI red except the clock phase's test.

## Notes

[2026-10-17T18:47:30Z · sase-1lh.7.5.4.3.3.2] PROPOSED FOLLOW-UP: sase agent list defaults to index_freshness=cached, which can omit a just-spawned ace-run after the first agent has already populated the index; the tutorial harness now falls back to on-disk agent_meta.json. A CLI/TUI revalidate-after-launch (or fail-closed empty-index) would make the second sase run visible without that fallback.

[2026-10-17T18:47:32Z · sase-1lh.7.5.4.3.3.2] Root cause: wait_for_launch polled sase agent list -j for status==RUNNING only. first-change is the second sase run in the same HOME; fakey can leave STARTING and reach DONE before the first RUNNING poll, and the default list omits completed agents. Fix is harness-only: snapshot names, poll list -a -j for any new name (STARTING/DONE included), fall back to agent_meta.json on disk when the listing index is stale, then sase agent wait. Timeout now includes sase run exit/stdout/stderr, list -a output, and HOME artifact state. Unit tests cover STARTING, already-DONE, disk fallback, and diagnostic payload. test_start_tutorials_pass_on_fakey passed 6 consecutive local runs (19-32s).

[2026-10-17T18:47:33Z · sase-1lh.7.5.4.3.3.2] PROPOSED FOLLOW-UP: Full CI 39046170656 Python 3.12 failed tests/ace/tui/test_statistics_pane_filters.py::test_reverse_range_cycles_backward_wraps_and_reenters_from_custom (wait_for 5.0s timeout); 3.13/3.14 on the same run passed it. Existing flake owner sase-1a2 (ready, +1). Not repaired here.

[2026-10-17T18:47:35Z · sase-1lh.7.5.4.3.3.2] Current reds at start (master 80f3dc7572): latest completed Master Gate 39047428622 fails only test_disabled_path_resurfaces_silenced_once_and_ignores_others (clock/sase-1ma). Latest completed Full CI 39046170656 fails that date bomb on 3.12/3.13/3.14, tutorial-tests (docs/start/first-change.md step 1, no agents appeared within 60s), and 3.12-only test_reverse_range_cycles_backward_wraps_and_reenters_from_custom. Tutorial job failed in 39009012994, 39011976162, 39046170656 and passed in 39020878025 (same SHA as the first two), 39028552949, 39031689155, 39043440193. PyPI still serves sase 0.17.1.

[2026-10-17T18:48:29Z · sase-1lh.7.5.4.3.3.2] Verified: tutorial harness waits for STARTING/DONE and on-disk agent_meta, dumps sase run plus HOME state on timeout. tests/test_tutorials.py unit tests plus 6 local fakey e2e passes. Date-bomb owned by clock/sase-1ma. Statistics flake recorded as sase-1a2 (Full CI 39046170656). epic-symbols empty.

[2026-10-17T19:20:49Z · sase-1lh.7.5.4.3.3.2--1] PROPOSED FOLLOW-UP: sase-1em — tests/test_agent_name_registry_rebuild_pending.py::test_registry_rebuild_keeps_live_identity_pending_claim failed once in just check ToolRun 0f42890b76eb8f5b313631becee5d80b (full parallel lane after core-identity-changed escalation; rebuild.call_count 1 vs 0). Isolation rerun passed (1 passed in 3.68s). Diff is tests/test_tutorials.py only; same load-only signature as sase-1em.

## Dependencies

- **Blocks:** [sase-1lh.7.5.4.3.3.3](sase-1lh.7.5.4.3.3.3.md) ◐ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.3.3.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.2.md) | [sase-1lh.7.5.4.3.3.2](sase-1lh.7.5.4.3.3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`60718e5`](https://github.com/sase-org/sase/commit/60718e5b1b77fcd89cdad2be8b016303a11f96d9) | fix(tests): wait for tutorial agents beyond RUNNING | [sase-1lh.7.5.4.3.3.2](sase-1lh.7.5.4.3.3.2.md) | 2026-10-17 15:31:32 EDT |

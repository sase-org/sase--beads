# Bead: sase-k3.6 — Land the epic

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.6` · **Size:** small
**Created:** 2026-08-12 11:38:55 EDT · **Closed:** 2026-08-12 14:55:09 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

land: re-measure the full budget in a real terminal against the phase `telemetry` baseline, file the named follow-ups with /sase_new_task, and close the epic with an honest reading of what each phase bought.

## Notes

[2026-08-12T18:49:50Z · sase-k3.6] PROPOSED FOLLOW-UP: after epic sase-k3, the agents loader's 'disk' stage is the largest remaining startup cost (p50 2.250 s of a 3.284 s visible_ready across 9 real-terminal master sessions) and epic sase-k3's budget model does not attribute it — the model accounted for badges (~0.40 s) and hidden-row repair (~0.26-0.39 s) inside it, both now removed. Component measurement on athena at master 1f388edee: the Tier-1 cached index query is only 0.280-0.464 s of it, and a full load_agents_from_disk_with_state() call warms to 0.81-0.94 s on repeat in the same process, so roughly 1.3-1.9 s is first-call loader work (dismissed-bundle snapshot, Patch snapshot, normalization/status overrides) that nothing in the plan or the three research passes measured. This is the next thing to attack if the <2 s visible_ready target still matters; it is NOT one of the six named follow-ups in plans:202608/ace_startup_critical_path.md, so it was recorded here rather than filed as a task. Recommend the owner file it (or fold it into task sase-kf, which currently only covers import).

[2026-08-12T18:55:09Z · sase-k3.6] Landed epic sase-k3. Re-measured the full budget in a real terminal (tmux, workspace .venv, live ~/.sase state) against the phase `telemetry` baseline, filed the named follow-ups, and did NOT close the parent epic (my launch prompt forbids it; the re-measured budget and corrections below are what an epic close should carry).

== METHOD ==
A/B between commit 59967cc06 (phase `telemetry` baseline: startup telemetry + the `imports` fix landed, `badges`/`repair`/`axe` not yet) and master 1f388edee, both run from the same workspace .venv against the same live ~/.sase state and the same locally-built sase_core_rs 0.26.5. Per run: one detached tmux window running `python -m sase ace`, per-run SASE_TUI_STARTUP_PATH / SASE_TUI_AGENT_LOADS_PATH / SASE_TUI_TRACE_PATH, SASE_TUI_LOADER_LOG_THRESHOLD_SECONDS=0.01, quit with `q` once the telemetry record landed. n=8 before, n=9 after; blocks interleaved (after, before, after) to bound load drift. 33 agent rows, 532 index rows, initial_tab=agents on every run.

HOST CAVEAT: athena was at loadavg ~30 on 64 cores throughout, with several sibling-epic agents running. Per the plan's own convention, absolute numbers are inflated (it estimated 15-40%); the A/B deltas are the portable result. Loadavg drifted only 35.0 -> 34.1 (15-min) across the whole capture, and the after-block was captured both before and after the before-block, so drift does not explain the deltas.
CORE CAVEAT: sase-core's `record_json`-removal from refresh_stale_rows is present in BOTH arms (it is unconditional), so the baseline arm is slightly faster than a true pre-epic tree. That biases against the epic, not for it.

== THE BUDGET, BEFORE AND AFTER (seconds, warm) ==
metric                          before p50   after p50    delta        before p95   after p95
process_start -> on_mount        0.660        0.669       +0.009        0.736        0.734
  (import; unchanged, as expected)
agents loader `disk` stage       3.351        2.250       -1.101 (-33%) 4.920        2.545  (-48%)
agents_ready (from proc start)   5.243        4.017       -1.226 (-23%) 7.004        4.226
axe_ready (from proc start)      1.943        1.782       -0.161 ( -8%) 2.033        2.082
visible_ready (from on_mount)    4.573        3.284       -1.289 (-28%) 6.327        3.575  (-43%)
all_surfaces_ready               4.573        3.284       -1.289 (-28%) 6.327        3.575  (-43%)

visible_ready and all_surfaces_ready are identical in every run because initial_tab is `agents` and Agents is the slower surface — exactly what phase `axe` predicted when it moved the stopwatch to the visible surface.

== TARGET: MISSED, AND BY HOW MUCH ==
The plan's target was warm Agents-tab time-to-interactive under 2 s with p95 under 2.5 s on athena. Measured: p50 3.284 s, p95 3.575 s. That misses by 1.28 s at p50 and 1.08 s at p95. Applying the plan's own 15-40% busy-host inflation allowance deflates p50 to roughly 2.0-2.8 s — at or above the target, still not under it. A projection that does not survive measurement is a finding: the epic bought a real ~1.3 s at p50 and ~2.8 s at p95, and did not reach the stated number.

Separately, the plan's phase-`repair` check "warm cached selection plus decode stays under 250 ms" measured 0.280-0.295 s warm — marginally over, on a busy host.

== WHAT EACH PHASE ACTUALLY BOUGHT ==
`telemetry` (sase-k3.1): the instrument this entire report is built on. Without tui_startup.jsonl there would be no before/after here at all, only component sums. Recording visible_ready from day one is what let phase `axe` move the stopwatch without invalidating the baseline. Highest-leverage phase in the epic.

`imports` (sase-k3.2): small and real. `python -X importtime -c "import sase.ace.tui.app"`, best of 3: pre-epic 875f67b74 = 2383 modules / 1.325 s self-time; master = 2375 modules / 1.300 s. Net -8 modules; the self-time delta is inside run-to-run noise, and process_start->on_mount is unchanged at p50 0.66-0.67 s. Both defects are gone at HEAD (verified: importing sase.logs.toast_log pulls no sase.axe module; importing sase.ace.tui.actions.patch._loading does not import unittest.mock), and tests/ace/tui/test_lazy_imports.py guards them.

`repair` (sase-k3.4): by far the largest win, and the plan UNDER-projected it by ~4-5x. Direct component A/B on today's live index (6,775 rows, 4,706 hidden, 103 MB), same process, same host: Tier-1 loader query with freshness="revalidate" = 1.861 s; with freshness="cached" = 0.464 s first call, 0.280/0.295 s warm. That is ~1.5-1.6 s removed from the loader, against a projected 0.26-0.39 s. It also accounts for essentially the whole measured visible_ready delta.

`badges` (sase-k3.3): removed from the critical path as designed; its cost is now a deferred, visible-rows-only background pass. Measured across the 9 master sessions (span agents.diff_badge_classification, source=apply): 11-12 candidates, 417 ms min / 643 ms p50 / 1035 ms max. Reported separately, per the plan: that ~0.6 s is new user-visible badge-settle latency, paid once per session (carry-over keeps refreshes from re-paying it), not a saving. I could not isolate the loader-side badge saving from the repair saving in this A/B because both phases are in the same "after" arm.

`axe` (sase-k3.5): structurally correct, magnitude does NOT reproduce — see corrections.

== CORRECTIONS TO THE RECORD ==
1. Badge cost is ~0.4 s, not the ~0.8 s the adjudicating research pass asserted. This is the plan's own re-measurement and I did not re-derive it independently; nothing in this phase contradicts it.

2. AXE's cost is a double ProjectSpec parse, not log tails / chop history / run snapshots. The ATTRIBUTION is confirmed and the summary/detail split the research prescribed was correctly not built. The MAGNITUDE does not reproduce on today's state, and this is a new correction: the plan measured find_all_patches() at 0.222 s warm and the double parse at ~0.41 s of a 0.543 s collect. Today the whole ProjectSpec archive is 339 patches in 16 .sase files totalling 1.1 MB and parses in 0.027 s. Measured at master vs the baseline commit, same host, same state:
     get_axe_status() warm:          0.075-0.087 s -> 0.022-0.026 s   (-0.053 s)
     collect_axe_status_data() warm: 0.136-0.178 s -> 0.075-0.088 s   (-0.07 s)
     count_hook_runners_global() (still uncached, by design): 0.027 s
     count_hook_and_agent_runners_global() (shared cached): 0.002 s
   So the real win is ~0.05-0.07 s per collect, about 1/6 of the projection — consistent with the 0.16 s axe_ready p50 delta. It is still worth having: it is paid on every 10 s refresh tick, not just startup, and it removes a cost that grows with archive size. Do not re-derive the 0.4 s figure from the plan; the archive it was measured against is not the archive that exists now.

3. New: the plan's budget model does not account for what is left. See the PROPOSED FOLLOW-UP note on this bead — the `disk` stage is still p50 2.250 s, of which the Tier-1 cached query is only ~0.3 s.

== PRODUCTION LOADER LOG: NO CONCLUSION AVAILABLE ==
~/.sase/logs/tui_agent_loads.jsonl (+.1), 8,173 records. Pre-epic (<16:15Z) `disk` p50: startup 2.663 s (n=462), auto_refresh 2.628 s (n=6,393) — reproduces the plan's recorded 2.663 / 2.637 exactly. Post-epic there are only 3 startup and 20 auto_refresh records, and the log is censored at >=2.0 s so these are percentiles of already-slow loads. Not enough data to claim anything; re-check after a few days of normal use. (My capture runs redirected this log per-run, so they are not in the production file.)

== FOLLOW-UPS ==
Filed with /sase_new_task, one at a time, each naming this bead. No semantic duplicates found (searched task beads by symbol/filename/error fragment, swept every task created in the last week across all statuses) and no in-progress epic (sase-j7, sase-jx, sase-k0, sase-k2, sase-jx.5, sase-k0.4, sase-jx.5.5) had a credible causal link.
1. sase-kf (xlarge, ready) — reduce the sase.ace import graph. Added a RELATED note pointing at closed/canceled sase-fy (497-module src/sase import cycle): related surface, different motivation and remediation, not a duplicate.
2. sase-kg (large, ready) — atomic-replace marker writes, then the directory-mtime gate, carrying the mandatory "rewriting a marker in place still triggers repair" test.
3. sase-kh (large, ready) — prune or archive hidden index rows; re-counted today at 4,706 hidden of 6,775, 103 MB. Cross-noted with sase-kg.
4. sase-ki (large, ready) — persist the diff-badge signature and result on the artifact row, carrying this phase's measured badge-settle numbers and an explicit instruction to re-measure per-branch byte volume rather than inherit sase-k3.3's qualified finding.
5. sase-kj (medium, ready) — cold-cache measurement; everything in this epic and all three research passes is warm-only.

… and 2380 more characters

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k3.2](sase-k3.2.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k3.3](sase-k3.3.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k3.4](sase-k3.4.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k3.5](sase-k3.5.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.6/README.md) | [sase-k3.6](sase-k3.6.md) | 0 |

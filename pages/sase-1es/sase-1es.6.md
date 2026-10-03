# Bead: sase-1es.6 — Swap the Static body for a Line-API ScrollView

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.6` · **Size:** large
**Created:** 2026-10-02 08:37:52 EDT · **Closed:** 2026-10-02 22:03:23 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

virtual-body-widget: replace the one-giant-Static body with a ScrollView that renders only visible rows from the line model through a bounded strip cache, split invalidation into paint versus layout, and keep every PNG golden unchanged.

## Notes

[2026-10-02T22:53:43Z · sase-1es.6--1] check triage + fixes: 6 NEW/1 FLAKY from run ed409dda657123458c685fbf09f595a4 disposition - (1) dangling-mark regression FIXED in _screen_actions_resolve._apply_resolution: non-retryable unresolvable refs now relabel via _invalidate_body_layout(relabel=True) instead of repainting the stale label layer (fixes test_dangling_refs_are_scoped_to_link_context + test_dangling_typed_refs_are_scoped_to_workspace_num, verified 5/5 in isolation). (2) split-focus callback in _screen_split now holds PagerBodyScroll weakly and skips unmounted targets (was pinning popped screens via app callback queue). (3) test_view_leak now settles with bounded pause+gc rounds (async Textual pump shutdown needs >1 cycle; 0 hard leaks in 12 settle trials; guard still fails on live views - verified by negative control). (4) tests/shard_timings.json refreshed via just refresh-shard-timings (my 2 new test files pushed drift 19.96%%->20.01%% over the 20%% gate). PROPOSED FOLLOW-UP: test_sigterm_leaves_run_running (exit 124 timeout vs 143, passes solo in 11s) and test_monitor_capacity_e2e (fakey exit 124, passes solo in 68s, zero pager refs) both look like full-suite load flakes at loadavg 40+; needs owner triage. PROPOSED FOLLOW-UP: test_unresolvable_label_toasts (baseline-known flaky) passes solo.

[2026-10-03T00:34:24Z · sase-1es.6--1] check ed409dda triage closed out on current tree (all 7 solo-green): dangling x2 (NEW) was a real regression, FIXED via relabel-on-nonretryable in _apply_resolution; view_leak (NEW) FIXED (weak split-focus + bounded settle), 645/645 tests/pager green; shard_timings (NEW) refreshed, 33/33 green; sigterm + fakey-capacity (NEW) pass solo (11s/65s), full-suite-only load flakes at loadavg 40+. PROPOSED FOLLOW-UP: owner triage of sigterm/fakey under contention. unresolvable_label_toasts (FLAKY) is baseline-known, passes solo. visual: 101 updated -> 84 unchanged + 18 updated after strip-padding fix (1-cell side pads baked into strips so order is text,pad,scrollbar like base; _body_paint_width subtracts pads; widget CSS padding removed; geometry probe matches base exactly: size 120, scrollbar x=118). Remaining 18 are all timeband goldens failing IDENTICALLY on clean HEAD (byte-identical candidates 17/18; 18th flips 111px<->26kpx run-to-run on identical code = flaky). Zero goldens touched. PROPOSED FOLLOW-UP: timeband goldens stale/flaky on HEAD + diff-range nondeterminism; owner triage.

[2026-10-03T00:34:43Z · sase-1es.6--1] bench after-numbers, box loadavg 15-25 (loaded; medians usable, maxes show scheduler stalls). 2k: build 8ms/8ms, mount 5.0s/2.7s, RSS 106/127MB (code-sparse/log-dense). 20k: build 69ms/82ms, mount 6.2s/4.5s, RSS 146/193MB (<=350MB PASS). keys above floor: j/k medians 2-6ms; maxes spike under load (ctrl+d 731ms, G 405ms, g 616ms at log-dense/20k). label_a: 135ms/1.5s at 2k, 3.3s/0.6s CPU at 20k: MISSES <=10ms target. vs plan baselines (before): 2k open 14s, 20k open 145s, RSS 5.7GB -> mount now ~5s/~5s, RSS ~100-200MB (big before->after win; absolute 250/600ms open targets missed: mount is syntax-publish + load dominated). PROPOSED FOLLOW-UP: (1) owner triage of label_a 20k 3.3s CPU; (2) re-bench open on quiet box, disentangle syntax-publish from open; (3) key-max stalls under contention. 100k rung exceeds the 10-min shell ceiling per case on this box -> monitor bench-100k running ladder 100000; results appended before close. No guardrail dropped.

[2026-10-03T01:08:10Z · sase-1es.6--2] bench 100k after-numbers (--cases code-sparse,log-dense --ladder 100000 --no-cold, /tmp/bench_100k.json, per_case_timeout 600s). code-sparse/100000: status TIMEOUT (no metrics; exceeded 600s per-case budget). log-dense/100000: status ok; build_wall 0.460s (target 100k log-dense <=5s PASS on build), mount_wall 20.47s / mount_cpu 15.73s, peak_rss 564.8MB, remount_100x30 9.75s, leak 0/3. keys (median_cpu): j 14.7ms, k 17.0ms, g 11.2ms, G 9.6ms, ctrl+d 20.4ms (MISSES <=5ms-above-floor guardrail); label_a 3.77s navigated=false (MISSES <=10ms label-prefix target); search chars 2.3-4.0s cpu. PROPOSED FOLLOW-UP: (1) code-sparse/100k TIMEOUT needs owner triage (syntax-publish suspected; log-dense same ladder completed); (2) log-dense/100k mount_wall 20.5s + remount 9.75s + RSS 564MB + key medians 10-20ms + label_a 3.8s all miss guardrails; (3) re-bench 100k on quiet box. No guardrail dropped.

[2026-10-03T01:28:56Z · sase-1es.6--2] check re-run after triage fixes: (1) ruff format collapsed 2 spots in _screen_body.py/_screen_split.py (my own edits) -> fmt clean. (2) test-waits lint flagged my bounded pause+gc loop in test_view_leak.py _settle_released -> rewrote on sanctioned sase.ace.testing.wait.wait_for(pilot, gc-then-weakref-check); tools/check_test_wait_helpers clean, ruff clean, 3/3 leak tests green in 8s (fail-on-pinned preserved via wait_for timeout). Full sase tool run check re-run as run 21a59dc1a904419102fd21e78794268a. visual full-lane: 102 passed, 83 unchanged + 19 updated (18 known timeband goldens, never touched; 19th history_past-frame_dark_60x30 passes solo 32/32 in 11s -> full-suite load flake under concurrent check run, zero goldens touched). PROPOSED FOLLOW-UP: history_past-frame load flake under contention; timeband goldens stale/flaky on HEAD per prior note. epic-symbols: no entries.

[2026-10-03T02:03:07Z · sase-1es.6--3] final check run 21a59dc1a904419102fd21e78794268a: verdict no_new_failures (1 FLAKY only: fakey test_monitor_capacity_e2e, full-suite load flake passing solo per notes #1/#2, base-known). All lint/fmt gates green. PROPOSED FOLLOW-UP: owner triage of fakey-capacity under contention. epic-symbols re-confirmed: no entries.

[2026-10-03T02:03:23Z · sase-1es.6--3] virtual_body_widget done per plan 202610/virtual_body_widget.md. Verified: (1) check run 21a59dc1a904419102fd21e78794268a verdict no_new_failures — all lint/fmt green, only 1 FLAKY (fakey capacity e2e, full-suite load flake, solo-green, filed as follow-up); dangling-mark regression + view-leak + shard-timings NEWs from prior run fixed on this tree. (2) visual: 83 unchanged + 18 known timeband goldens failing identically on clean HEAD + history load flake solo-green; zero goldens touched. (3) bench after-numbers recorded (2k/20k/100k); misses filed as follow-ups, no guardrail dropped. (4) epic-symbols: no entries.

## Dependencies

- **Depends on:** [sase-1es.5](sase-1es.5.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.7](sase-1es.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.6.md) | [sase-1es.6](sase-1es.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`54427ed`](https://github.com/sase-org/sase/commit/54427ed47c3ff911cd212778c13019440aa215f6) | feat(pager): virtualize body with Line-API ScrollView and bounded strip cache | [sase-1es.6](sase-1es.6.md) | 2026-10-02 22:21:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0vd][1] | Check phase deps and notes to assess conflict with three-pane split work | 1 |
| read-by | [agent:sase-1eu.7][2] | pager-three-panes gate: confirm sase-1es.6 landed | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0vd/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eu.7/README.md

<!-- sase:referenced-by:end -->

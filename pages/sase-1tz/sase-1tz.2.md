# Bead: sase-1tz.2 — Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.2` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST · **Closed:** 2026-11-20 09:02:14 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

noise: give agent_publication per-(project, signature) backoff with standing alerts, a bounded incremental drain, and a terminal state for unrestorable prompt archives. Aggregate the error ring and digests by signature with durable true counts and pruning. Cut measured TUI GC pauses and main-thread I/O stalls, with tui_stalls.jsonl as the acceptance metric.

## Notes

[2026-11-19T16:46:45Z · sase-1tz.2.1.4] pub_cleanup (sase-1tz.2.1.4): athena 2 Nov-3 `.sase-v2-*` dirs + 27 archive notices; apollo 0 scratch + 3 notices; cleanup cap 15s from athena p50≈1.6/max≈11.8; live sweep gated.

[2026-11-19T16:56:41Z · sase-1tz.2.1.1] error_groups (sase-1tz.2.1.1): ring baseline athena 100 rows/44 publication (Nov14-19), apollo 100 rows/61 publication (Nov17-19); counts durable in error_counts.json after install.

[2026-11-19T18:28:52Z · sase-1tz.2.1.2] digest_render baseline: athena 729 files / 14.5 MiB; apollo 440 files / 23.6 MiB. After-install: ls ~/.sase/axe/error_digests | wc -l; tail -n 30 "$(ls -t ~/.sase/axe/error_digests/* | head -1)"

[2026-11-19T19:52:00Z · sase-1tz.2.1.11] ui_io_offload (sase-1tz.2.1.11) apollo baseline, read-only tui_stalls.jsonl{.1,} Nov 16-19: 1717 recovered stalls, 1255 low-GC (gc_overlap_s<1), max 116.8 s. Target frames in stall-start stacks: _launchable_mru_tick->_stat_token n=2 max 115.8 s; hijack _canonical_path n=117 max 9.9 s (footer/leader _schedule_hijack_decision); load_project_alias_map n=144 max 11.1 s (hot caller rearm_live_agent_watch_coverage->Agent.get_artifacts_dir->resolve_project_alias_ref; list_project_records 120, _project_record_has_spec 25). After-install: ssh apollo python3 - <INSTALL_EPOCH> < ui_io_offload_stalls.py (attached); target n=0 for all three after the install epoch.

🔒 ui\_io\_offload\_stalls.py

[2026-11-19T19:55:09Z · sase-1tz.2.1.8] stall_telemetry (sase-1tz.2.1.8): before install, athena tui_stalls.jsonl is 38.3 MB + 2.1 MB .1 (0 torn) and tui_faults.log 17 KB of headers only; apollo is 16.7 MB + 2.1 MB (3 torn) and 14.8 KB. After install, the stall log is capped at 24 MiB/segment (>= 48 h; athena replays at 19.8 MiB/48 h), and tui_faults.log gets headers only for real faults. The after-install commands are in the sase-1tz.2.1.8 measurement note.

[2026-11-19T22:32:32Z · sase-1tz.2.1.10] heap_retainers one-liner: fixed the top TUI-owned retainer (skill-use whole-file snapshot cache -> targeted scan, 11,360 retained -> <=50, cold miss 3.6x faster) and added SkillUseEvent census tracking; notification +1 TUI bound and freed per-type census left as follow-ups.

[2026-11-19T22:53:18Z · sase-1tz.2.1.13] TUI acceptance evidence: before install (phase notes .9/.11), athena gen2 max 324.224s (backstop; idle max 74.773s), apollo max sampled low-GC stall 116.8s, 24h heartbeat RSS peaks athena 5.83GB / apollo 3.87GB. Current tree HEAD 225bfb7ff2 benches: j/k suite 8 fail / 11 pass (582.76s); trace suite 1 fail / 6 pass (79.45s), with deterministic legacy clan-wave test mismatch noted on phase sase-1tz.2.1.13. Available live instance 01f377a7 is only partial and older source_revision 49b96a9c (pre-HEAD), with 23.4m diagnostic window: max observed hitch 2.324s, no gen2 collection samples (max pause unavailable), GC share 5.47%, heartbeat RSS 1.40GB -> 4.09GB, swap 0; report is INCOMPLETE (no post-warmup paired intervals/four-hour span). Do not treat as after acceptance. After human install of HEAD and TUI restart with SASE_TUI_PERF=1, run tools/tui_freeze_report --acceptance --instance <new-id> --since <post-warmup-start> --until <end> -b <representative-busy-hour-start> -e <busy-hour-end> -t agents; require >=4h gap-free coverage and retain full JSON report. Related task beads remain open: current evidence does not demonstrate resolution.

[2026-11-20T11:39:09Z · sase-1tz.2.1.13] tui_acceptance (sase-1tz.2.1.13) before/after. BEFORE (pre-install, phase notes .9/.11): athena max GC pause 324.2 s (backstop; idle max 74.8 s, p95 3.26 s), max stall 331 s, 24 h RSS peak 5.83 GB; apollo max gen-2 8.26 s (idle max 4.29 s, p95 1.79 s), max low-GC stall 116.8 s, RSS peak 3.87 GB. AFTER (12-13 h mostly idle soaks of build 49b96a9c50 = every TUI phase except heap_retainers): athena 01f377a7 max GC pause 18.94 s (automatic gen-2 on a worker thread; policy idle max 0.95 s, p95 0.86 s), max stall 20.17 s, RSS peak 5.69 GiB, VmSwap max 975 MB; apollo f9fc07ea max GC pause 7.82 s (rss_backstop; idle max 1.50 s, p95 0.74 s), max stall 8.61 s, RSS peak 3.32 GiB, swap 0. Acceptance: GC share 2.21%/1.34% and hitch share 0.12%/0.06% PASS; idle p95, late hitch, and 4 h RSS growth FAIL on both; athena VmSwap FAIL; busy hour INCOMPLETE. ui_io_offload targets are n=0 on both hosts. sase-1nc, sase-1gf, and sase-lx stay open with evidence notes. HEAD fb85972f27 went live 2026-11-20 (athena 477637e5, apollo df9973ba). AFTER-INSTALL: after >=4 h on HEAD including one active Agents-tab hour, run on athena: tools/tui_freeze_report --acceptance -j --instance 477637e5 --since <start+20m> --until <end> -b <busy-start> -e <busy-start+1h> -t agents; on apollo: ssh apollo "cd ~/projects/github/sase-org/sase && tools/tui_freeze_report --acceptance -j --instance df9973ba --since ... --until ... -b ... -e ... -t agents". The full JSON reports are attached to sase-1tz.2.1.13 note #2.

[2026-11-20T14:03:37Z · sase-1tz.2.1.land] PHASE VERIFICATION (sase-1tz.2.1 remaining-work lander; this phase auto-closed as 'delegated work landed' when child epic sase-1tz.2.1 closed). Verified the child plan completed the phase's work: (a) publication de-flap with standing alerts and backoff: 2.1.3 plus remaining-work item 2 (core decider ignores volatile detail; *publisher* alerts for listing/target failures; deferred projects not counted per tick; doorbell honors backoff) and item 3 (doctor WARNs on alerts without stuck rows); (b) bounded drain with completing cleanup: 2.1.4 cleanup budget + scratch sweep, 2.1.5 inventory reuse/scoped queries, plus item 6 multi-batch one-build test; (c) terminal state for unrestorable prompt archives: 2.1.6 plus item 1 bounded per-pass sweep that retires already-quarantined rows (athena 369 / apollo 263 rows drain at <=25 per project per pass after install); (d) signature-grouped error ring and digests with durable counts and pruning: 2.1.1/2.1.2 plus item 4 (lock and ring-reset failures now counted, Python fallbacks and dead last_error_digest_ts code removed); (e) TUI GC and I/O stall reduction with tui_stalls.jsonl as the metric: 2.1.8-2.1.13 plus item 5 paging-pressure GC gate (evidence on sase-1nc). Before-numbers and after-install commands are present in notes #1-#8 of this bead. Verification: sase tool run check d3adc7ab6cd66e963ccabbaf4b676910 succeeded (full-suite escalation); sase-core check ccbc1dc8fab68b9a0f8a1c473d8c75ec succeeded; the core standing change reaches sase through the core pin ratchet. LIVE AFTER-INSTALL ACCEPTANCE IS STILL PENDING HUMAN INSTALL: run the after-install commands in note #8 (tools/tui_freeze_report --acceptance on athena and apollo) plus notes #2/#3/#5 ring/digest/stall checks. Epic sase-1tz is not closed here; its land agent owns it.

## Attachments

- 🔒 ui\_io\_offload\_stalls.py · text/x-python · 1.67773 KiB (private attachment)

## Dependencies

- **Depends on:** [sase-1tz.1](sase-1tz.1.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.3](sase-1tz.3.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) | [sase-1tz.2](sase-1tz.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.11][1] | Need sibling phases' measurement-note format before recording ui_io_offload before-numbers on sase-1tz.2 | 1 |
| read-by | [agent:sase-1tz.2.1.land][2] | Need the parent phase notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.land.md

<!-- sase:referenced-by:end -->

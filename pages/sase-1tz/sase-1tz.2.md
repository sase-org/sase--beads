# Bead: sase-1tz.2 — Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.2` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST
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

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.11/README.md

<!-- sase:referenced-by:end -->

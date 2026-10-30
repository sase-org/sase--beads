# Bead: sase-1nf.14.1.7 — Verify busy-hour and four-hour acceptance on fixed code

[Bead Pages](../README.md) / [sase-1nf.14.1](sase-1nf.14.1.md) / sase-1nf.14.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.14](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.md) · **Assignee:** `sase-1nf.14.1.7` · **Size:** medium
**Created:** 2026-10-24 13:37:45 EDT · **Closed:** 2026-10-28 18:51:37 EDT
**Plan:** [202610/measured\_tui\_gc\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/measured_tui_gc_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:769389ddf92f78aeab5bcd7e | attached via sase artifact create --bead |
| related | file:explicit:8ce7eae6df0b33fe4d6aae99 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

fixed-capture: verify installed revisions and user restarts, preflight real navigation, capture representative interaction and four-hour coverage on both hosts, and publish results.

## Notes

[2026-10-27T16:18:13Z · sase-1nf.14.1.7] 2026-10-27 UTC preflight: Athena instance c21243a9 PID 2041351/start_ticks 77062375, boot 2e013859-5e29-418c-bf6d-035a5eeff435; Apollo instance be9f17e4 PID 4013465/start_ticks 150618699, boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96. Both load source 3b99dac0a0bdafc3dcce6e0737bc88c8d925251c and have SASE_TUI_PERF/SASE_TUI_GC_CENSUS unset; neither has current-instance j/k rows. Both runtimes are SASE 0.18.1, Textual 8.2.8, Rich 15.0.0, sase-core-rs 0.43.0; Athena Python 3.14.7, Apollo Python 3.12.3. Capture paths: ~/.sase/logs/tui_startup.jsonl, ~/.sase/logs/tui_stalls.jsonl[.1], ~/.sase/perf/tui_jk.jsonl. Dry runs on both target 0.18.1+59.g691ef461 (which contains fixed backstop commit 353d833bf0) and sase-core-rs 0.43.0+1.g6d11122ee; updater warns six agent runners. Next: reviewed human update gate, then user-owned TUI restarts and immediate telemetry preflight.

[2026-10-27T17:44:15Z · sase-1nf.14.1.7--2] Post-restart preflight (2026-10-27 UTC): Athena app instance 14097559 (PID 2041351, boot 2e013859-5e29-418c-bf6d-035a5eeff435, /proc start_ticks 77062375, startup 17:10:29Z) and Apollo app instance c1862a96 (PID 4013465, boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96, /proc start_ticks 150618699, startup 17:36:22Z) both report source revision 8d41b722182145e16bf572b1d3a76a2fffad0f4c, whose ancestry includes fixed backstop 353d833bf0. Neither live process environment contains SASE_TUI_PERF or SASE_TUI_GC_CENSUS. Their instance IDs have GC/memory telemetry but zero attributable tui_jk rows and zero prompt_activity rows. No acceptance capture started; need a user-owned relaunch with the probe variables in the actual TUI process before proceeding.

[2026-10-28T18:31:01Z · sase-1nf.14.1.7] 2026-10-28 18:27 UTC read-only preflight: fixed code has landed and is live on both hosts (startup source d12d712e792a3b496015a72e0a4ecb1ed838245f; local ancestry confirms quiet-policy 353d833bf0 and render fix 0d11a115db). Athena instance 8ec653a0, PID 2041351/start_ticks 77062375, boot 2e013859-5e29-418c-bf6d-035a5eeff435; Apollo 84d61eeb, PID 4013465/start_ticks 150618699, boot 1e87418e-2b01-47ab-ad0d-eb23a80d5f96. Both started around 18:19Z and still have SASE_TUI_PERF and SASE_TUI_GC_CENSUS unset; both have zero current-instance perf and prompt_activity rows. Installed executable environments report SASE 0.18.1, core-rs 0.43.0, Textual 8.2.8, Rich 15.0.0; live heartbeat Python Athena 3.14.7/Apollo 3.12.3. Process/log witnesses and installed-package provenance retained at file:explicit:769389ddf92f78aeab5bcd7e. This is incomplete preflight, not acceptance. Previous remainder is operational and fits the existing questions/monitor workflow without a new coding epic. Next: user-owned shell relaunch with both flags, immediate real navigation/prompt/modal preflight on each host, confirm usual tabs and representative busy hour, then 20-minute warmup and retained four-hour same-instance capture via monitor; retain those instances for phase .8. No code changes or new installation required for this preflight.

[2026-10-28T22:33:43Z · sase-1nf.14.1.7--1] 2026-10-28 fixed-code assessment after answered gate 6faea19e-df8a-410d-a167-94ebfc7c5a5f: both live processes now have SASE_TUI_PERF=1 and SASE_TUI_GC_CENSUS=1, source 196690f6cb4f3ddc89f0cfa18817688fd2675fed; ancestry includes 353d833bf0 and 0d11a115db. Athena instance 8b65de59 / PID 4045198, Apollo 7e973b00 / PID 1562336, both started about 20:45 UTC. Raw logs, process witnesses, source provenance, frozen reporter, text/JSON results, commands and independent assertions: file:explicit:8ce7eae6df0b33fe4d6aae99. Report: research:202610/tui_gc_fixed_capture_20261028.md.

Current result is FAIL with INCOMPLETE acceptance coverage, not a completed four-hour capture. Post-warmup observed envelopes span 4520.850/4516.190 s. Full-GC row/heartbeat counts match 60/60 and 70/70. All six retained acceptance commands exit 1. Independent assertions reproduce sums, sorted quantiles, counts, and modern-instance attribution. No source changes or test-suite verification needed; research Markdown whitespace checked. No epic-symbol entries remain.

PROPOSED FOLLOW-UP: Fixed code still misses both-host GC and hitch targets — on separately validated contiguous fragments of 3312.840 s (Athena) and 3912.897 s (Apollo), idle full-GC p95 is 3.929704/0.907595 s (limit 0.5), GC share 11.7889%/4.0104% (limit 3%), and loop-hitch share 14.7488%/0.6271% (limit 0.5%). Athena sampled swap reaches 4567040 B (limit zero). Live source and evidence ref above. Census remains included; retained graph/render/cache populations support further ownership/update-cadence investigation but do not establish allocation shares or a leak. Waiting alone will not repair the measured failures.

PROPOSED FOLLOW-UP: Review heartbeat coverage rejection separately from actual missing accounting — one interval per host exceeds the reporter absolute 302 s cap (304.093773/302.767774 s), although its recorded window_s agrees within 0.397442/0.062046 s and full-GC counters agree with emitted rows. No guard or verdict was changed; evidence above preserves a potential delay-versus-loss diagnostic issue for the land agent.

User asked: "Try to get this epic closed without any more waiting." No further monitor or question gate was started. This is not treated as an acceptance waiver. Phase .7 remains open explicitly because the original contract is unfinished; no ancestor or .8 was closed. Required outstanding evidence: four contiguous hours per instance, representative Agents hour (current observed n=31/9, p95 838.889/210.243 ms; best candidate hours only 30/8 actions in three bins), declared normally used tabs, Apollo prompt/text-entry active versus idle evidence, and .8's same-instance 24-hour soak. Athena prompt state evidence is present. The current snapshots preserve evidence for land-agent triage but no ongoing retention monitor is running; future log rotation can remove subsequent live evidence. No passing or complete measurement claim is made.

## Dependencies

- **Depends on:** [sase-1nf.14.1.6](sase-1nf.14.1.6.md) ✓ · ⧖ 2026-10-24
- **Blocks:** [sase-1nf.14.1.8](sase-1nf.14.1.8.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.14.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.7.md) | [sase-1nf.14.1.7](sase-1nf.14.1.7.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.14.1.7--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.14.1.7.md

<!-- sase:referenced-by:end -->

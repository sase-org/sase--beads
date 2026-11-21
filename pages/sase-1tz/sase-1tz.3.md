# Bead: sase-1tz.3 — Targeted high-confidence defect fixes (items 6-10)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.3` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST · **Closed:** 2026-11-20 13:37:49 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

defects: add the prompt_prose artifact-link wire variant with a binding contract test, close the remaining runtime-update races, fix Telegram fallback, retry, and scope semantics, keep provider instruction bundles under their caps with a size gate, and advance bead_task_triage's generation on request_id_conflict.

## Notes

[2026-11-20T14:30:34Z · sase-1tz.3.1.8] tg_scope (sase-1tz.3.1.8): telegram outbound routine now athena-only in chezmoi source; apollo was wasting 12.7 tg_outbound ticks/min.

[2026-11-20T14:32:32Z · sase-1tz.3.1.5] prebuild_miss (sase-1tz.3.1.5): apollo baseline 23/45 prebuild attempts were commit-mismatch misses with nonzero consume rc (was 18/37 in the audit).

[2026-11-20T15:47:59Z · sase-1tz.3.1.2] swap_repro (sase-1tz.3.1.2): the update-overlap reproducer landed with 6 strict xfails for swap_chop_guards and swap_launch_guards. Before install, every overlap failure fell within 120 s of an update (athena 6 of 6, apollo 4 of 4, last 7 days); all 6 SIGBUS exits started during the maturin-develop rebuild step, and no install path rewrites files in place. Re-measure after install with tools/swap_overlap_census (command on sase-1tz.3.1.2).

[2026-11-20T16:04:05Z · sase-1tz.3.1.7] tg_degraded (sase-1tz.3.1.7): athena before = 456 TimedOut + 700 traceback lines in lumberjack-telegram.log (Nov 16-20) and 653 receiver tracebacks + 59 credential-retry lines; apollo 0/0. Outbound and receiver now log one line per degraded-state transition; after-install command is on sase-1tz.3.1.7.

[2026-11-20T16:20:00Z · sase-1tz.3.1.9] bundle_trim (sase-1tz.3.1.9): bob-cli Codex root bundle 36,225 -> 30,097 bytes via compile-time compaction step superseded_summaries (fits 32 KiB); sase bundles byte-identical; repeat command recorded on sase-1tz.3.1.9.

[2026-11-20T16:38:55Z · sase-1tz.3.1.1] prose_wire (sase-1tz.3.1.1) measured on athena: 3 quarantined publication requests for sase-1tj.land fail on prompt_prose for plan:202611/research_commit_gap.md; 0 prompt_prose rows are stored; no standing alert because quarantine stopped retries. After install, run sase agent sync -p sase -q, then use the check command on sase-1tz.3.1.1.

[2026-11-20T16:40:55Z · sase-1tz.3.1.10] bundle_gate (sase-1tz.3.1.10): Codex oversize fallbacks before install = athena 212 events / apollo 230 over 2026-11-13..20; new deep doctor check instructions.bundle_size reports bob-cli/codex WARN (compacted to 30,392/32,768). Repeat command recorded on sase-1tz.3.1.10.

[2026-11-20T18:37:22Z · sase-1tz.3.1.land] triage_conflict (sase-1tz.3.1.11), recorded by the sase-1tz.3.1 land agent because the phase skipped this summary: the baseline was 0 'request id already belongs to a different gate specification' lines in the 11 bead_task_triage run logs athena retained from the prior 7 days. The audit's 1,517 lines had rotated out. A conflict now cancels the stale pending gate, advances and persists the generation, and retries once per pass. The repeat command is on sase-1tz.3.1.11 note #1.

[2026-11-20T18:38:14Z · sase-1tz.3.1.land] Verified by the sase-1tz.3.1 land agent: child epic sase-1tz.3.1 completed every part of this phase's scope.
- prompt_prose: sase-core variant 09391374 is pinned, and the host-origin binding contract test is in place.
- Runtime-update races: the swap reproducer has no xfail left; chop, launch, and finalizer guards defer and retry; a prebuild cache miss is a miss.
- Telegram: parse-only fallback with per-chunk retry and resume (sase-telegram 60a94ab), one notice per degraded-state transition (ceffb63), and the outbound routine runs only on athena (chezmoi 3623450f).
- Provider bundles: compile-time compaction plus the instructions.bundle_size doctor check and the just-check gate.
- bead_task_triage advances its generation on request_id_conflict.
The focused suites passed 278/278 on HEAD f6b4344d87. Follow-up triage is in the sase-1tz.3.1 close note. Live acceptance is human-run: install, chezmoi apply, and sase agent sync -p sase -q, then the per-phase after-install commands.

## Dependencies

- **Depends on:** [sase-1tz.2](sase-1tz.2.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.4](sase-1tz.4.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) | [sase-1tz.3](sase-1tz.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.land][1] | Need the parent link and phase scope/notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.land/README.md

<!-- sase:referenced-by:end -->

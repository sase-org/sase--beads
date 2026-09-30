# Bead: sase-1cx.7 — Agent guidance, docs, live harness case, and flag removal

[Bead Pages](../README.md) / [sase-1cx](README.md) / sase-1cx.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u3.md) · **Assignee:** `sase-1cx.7` · **Size:** medium
**Created:** 2026-09-29 20:32:22 EDT · **Closed:** 2026-09-30 15:11:31 EDT
**Plan:** [202609/tool\_run\_escalation.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_run_escalation.md)

## Description

guidance-and-flag-removal: delete the flag's Off branches and close its bead. Rewrite the Muse single-turn directive and the `sase_monitor`/`sase_final` skill sources for inline-then-escalate, finish the cross-cutting docs, and add the live escalate-then-join harness case.

## Notes

[2026-09-30T18:53:00Z · sase-1cx.7] Live escalate-then-join report: full tools/smoke_sase_tool_runs --live passes (failed=0 not-run=0, DoD-17 pass incl. new dod-17-live-escalate-join); text log /tmp/live_full.log, JSON /tmp/live_escalate_join.json. Case: detached run from simulated agent (fixture-agent + sacrificial sleeper pid), real sase monitor start -J (join_exit=0, runner group killed), one run id end-to-end (run 732e8540..., monitor 824c2fbhwdk9), mirrored exit failed/3, join record names the monitor.

[2026-09-30T18:55:17Z · sase-1cx.7] PROPOSED FOLLOW-UP: tests/completion/test_kind_coverage.py::test_every_value_slot_is_kinded_choiced_or_hinted (monitor/start:join slot uncaptioned, from phase sase-1cx.5 -J addition) and tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list both fail identically on the clean base tree; not caused by this phase.

[2026-09-30T18:58:47Z · sase-1cx.7] PROPOSED FOLLOW-UP: just check feature-flags lint fails on rule 7 for unrelated flag public_bead_attachments (bead sase-1dg closed 2026-09-30T18:54:57Z by another epic without removing its registry definition); this phase touches neither that flag nor that bead.

[2026-09-30T19:00:58Z · sase-1cx.7] PROPOSED FOLLOW-UP: just check symvision lint fails at HEAD on private imports unrelated to this phase (_scanner_rules_version in src/sase/bead/attachments/audience.py, _store_growth_lines in src/sase/bead/attachment_doctor.py); this phase touches neither file.

[2026-09-30T19:11:31Z · sase-1cx.7] Phase done and verified: tool_run_escalation Off branches deleted (detach, budget, inline-escalation, monitor -J gates), registry entry removed, flag bead sase-1dc closed, feature-flags lint clean for this flag. Muse directive rewritten (tool-run exception, no timeout wrap, -J next step); sase_monitor/sase_final skills updated with -J guidance; docs reworked (tool Inline-then-escalate story, monitors join, llms Muse section, no beta wording left). New live harness case dod-17-live-escalate-join passes; full smoke --live green (failed=0 not-run=0). Tests: 68+39 focused tool/monitor/llm tests pass, 491 pass in skill/flags/completion/smoke-twin files. Pre-existing/external failures recorded as PROPOSED FOLLOW-UP notes (2 completion tests fail on clean base; symvision bead-attachments imports at HEAD; sase-1dg rule-7 race). just check stops at the external sase-1dg flag lint; all other gates (ruff, mypy, fmt, pyscripts, test-waits, changelog, patch-stitch, committed-plans) pass.

## Dependencies

- **Depends on:** [sase-1cx.5](sase-1cx.5.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1cx.6](sase-1cx.6.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cx.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.7/README.md) | [sase-1cx.7](sase-1cx.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f3899b4`](https://github.com/sase-org/sase/commit/f3899b4171773a901037992a3788c1a9490e75a5) | feat(tool): remove tool\_run\_escalation flag and land inline-then-escalate guidance (sase-1cx.7) | [sase-1cx.7](sase-1cx.7.md) | 2026-09-30 15:14:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cx.7][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1d5.8--1][2] | check flag owner epic | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cx.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.8.md

<!-- sase:referenced-by:end -->

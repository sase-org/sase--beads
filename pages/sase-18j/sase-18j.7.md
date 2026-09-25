# Bead: sase-18j.7 — Continue past all-KNOWN stages by default for agents

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.7` · **Size:** medium
**Created:** 2026-09-24 19:07:11 EDT · **Closed:** 2026-09-25 16:24:40 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

## Description

known-gated-continuation: add the hidden _triage-stage verb and the bounded fail-safe run_silent decision, and make known mode the default for agent-attributed runs of run_silent tools behind the flag.

## Notes

[2026-09-25T20:23:09Z · sase-18j.7] PROPOSED FOLLOW-UP: symvision gate red on clean tree — private _OwnerRecordLookup import in src/sase/bead/cli_work_cleanup_targets.py; reproduces with changes stashed

[2026-09-25T20:23:24Z · sase-18j.7] PROPOSED FOLLOW-UP: just check _setup fails — linked sase-core origin/master (2457913) reports agent-artifacts schema 10 vs tools/validate_sase_core_rs expecting 9; sase pin c31b8cf is behind

[2026-09-25T20:23:46Z · sase-18j.7] PROPOSED FOLLOW-UP: footer renders stopped marker as stopd not stopped (triage_display._stage_line appends d to stop); cosmetic, from closed phase record-and-render

[2026-09-25T20:24:05Z · sase-18j.7] PROPOSED FOLLOW-UP: test_handoff_end_to_end_publishes_one_notification hit tool run store is busy under wide parallel load, passes alone; possible launcher-poll vs worker-settle contention window

[2026-09-25T20:24:40Z · sase-18j.7] Known-gated continuation done: hidden _triage-stage verb (continue iff >=1 item, all KNOWN/FLAKY), helper known path with 10s fail-safe bound (timeout/crash/unparseable stop), known default for agent-attributed runs behind tool_failure_triage (foreground + adopted-worker recorded agent; humans/flag-off/-x stay never), fingerprint_before persisted at observe so mid-run triage reads base(R), decisions + continuation_extra_ms persisted at settle and visible in show -j. Verified: 11 new tests in tests/tool/test_known_continuation.py + parser hidden-verb test green; neighbors green (keep_going/executor/settlement/query/handoff 103, settlement file 39); ruff + mypy clean on touched files; live e2e shows verdict no_new_failures with KNOWN witness. Epic-symbols clean. Two pre-existing reds recorded as PROPOSED FOLLOW-UP (symvision private-import, _setup core schema 10-vs-9 drift) — both reproduce without this diff.

## Dependencies

- **Depends on:** [sase-18j.6](sase-18j.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.9](sase-18j.9.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18j.7/README.md) | [sase-18j.7](sase-18j.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d17a753`](https://github.com/sase-org/sase/commit/d17a7534ad595b45e7076755e0ddd84c1d378460) | feat(tool): known-gated continuation for agent runs | [sase-18j.7](sase-18j.7.md) | 2026-09-25 16:27:31 EDT |

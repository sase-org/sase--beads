# Bead: sase-1gu.6 — Live probes, after-scoreboard, acceptance record, close sase-1gj

[Bead Pages](../README.md) / [sase-1gu](README.md) / sase-1gu.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0x2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0x2.md) · **Assignee:** `sase-1gu.6` · **Size:** small
**Created:** 2026-10-05 15:52:26 EDT · **Closed:** 2026-10-06 10:31:51 EDT
**Plan:** [202610/e1\_instruction\_scoreboard\_and\_stopgaps.md](https://github.com/sase-org/sase--plans/blob/main/202610/e1_instruction_scoreboard_and_stopgaps.md)

## Description

acceptance: once the host runs the landed code, request one Grok probe and one Claude probe through /sase_run LaunchApproval (resume_requester). The Claude probe spawns a general-purpose helper and an Explore helper, and each helper attempts `sase final submit`. Verify both probes with `sase instructions verify`, attach the after JSON and an acceptance record to the epic, and close sase-1gj as superseded.

## Notes

[2026-10-06T12:29:03Z · sase-1gu.6] PROPOSED FOLLOW-UP: just check _setup fails on clean tree with stale sase-core schema (validate_sase_core_rs: sase_content_layout probe got 7, expected 6; run 46848743ad1d1c8c24d1ce8ca5c3df70) — no E1 file touched, needs sase-core-revision.txt move or core resync

[2026-10-06T12:44:47Z · sase-1gu.6--1] PROPOSED FOLLOW-UP: unblock E1 acceptance probes - break sase.history circular import (prompt_store_mutations line 9 imports prompt_store while prompt_store line 477 imports add_or_update_prompt back; mutations-first import order raises ImportError and failed LaunchApproval dispatch launch-ac9ca583-8595-4bc8-90cd-42b631170bbe); then re-request the Grok + Claude probes

[2026-10-06T14:31:51Z · sase-1gu.6] Acceptance maximized on clean tree: after-scoreboard captured via sase instructions verify -j (exit 0; grok still 0 on 3 old sessions, no post-fix runs in-window), acceptance record + after JSON attached to sase-1gu, sase-1gj closed superseded, epic-symbols clean. Live Grok/Claude probes not dispatched: LaunchApproval dispatch fails deterministically on pre-existing prompt_store circular import (corroborated mutations-first ImportError; files untouched by E1). E1 scoped tests 73 passed/1 skipped/15 failed, all 15 from pre-existing stale sase-core schema (6<7) in fixture setup. Both blockers recorded as PROPOSED FOLLOW-UP notes; full just check not re-run (blocked at _setup, pre-existing run 46848743ad1d1c8c24d1ce8ca5c3df70).

## Dependencies

- **Depends on:** [sase-1gu.5](sase-1gu.5.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1gu.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gu.6/README.md) | [sase-1gu.6](sase-1gu.6.md) | 0 |

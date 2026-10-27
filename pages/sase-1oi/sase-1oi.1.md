# Bead: sase-1oi.1 — Commentary tail in the Muse adapter

[Bead Pages](../README.md) / [sase-1oi](README.md) / sase-1oi.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.2i.linker.w0` · **Assignee:** `sase-1oi.1` · **Size:** medium
**Created:** 2026-10-26 15:05:47 EDT · **Closed:** 2026-10-26 23:08:38 EDT
**Plan:** [202610/muse\_commentary\_live\_reply.md](https://github.com/sase-org/sase--plans/blob/main/202610/muse_commentary_live_reply.md)

## Description

commentary-tail: add a fail-soft session-log tail driven by a new on_tick hook in stream_json_lines, write each root-run commentary message as its own live_reply.md chunk, record muse_session_id at launch, add the terminal-text fallback, cover it with unit and temporal tests, and update the Muse provider docs.

## Notes

[2026-10-26T19:53:53Z · sase-1oi.1] PROPOSED FOLLOW-UP: skipped decision record — auto-plan left decision_record=no, so do not add decisions:private-logs-display-only (private session logs may feed display-only fail-soft surfaces, never control flow, returned content, or completion; link [[decisions/adapters-normalize-harnesses]]; reopens when muse exec --json exports message phase or stream parsing moves to sase_core)

[2026-10-26T19:54:27Z · sase-1oi.1] PROPOSED FOLLOW-UP: retire the commentary tail once muse exec --json exports message phase — parse the new event in _process_muse_json_line, dedupe by message_id against the tail during the transition, then delete _muse_commentary_tail.py and the on_tick call site

[2026-10-27T03:08:27Z · sase-1oi.1] PROPOSED FOLLOW-UP: tests/test_core_agent_scan_options.py::test_capacity_only_skips_done_dirs_and_keeps_active_ones fails identically on the clean base tree — TS_HOME_RUNNING 20260427100000 missing from capacity_only scan results {20260427150000, 20260427170000, 20260427180000}; reproduced after git stash of this phase

[2026-10-27T03:08:33Z · sase-1oi.1] PROPOSED FOLLOW-UP: tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited flaked once under high load in ToolRun 307a0c857ef60b738f085e57c3c933cd (got timeout, wanted rate_limited); passed on rerun; does not use stream_json_lines

[2026-10-27T03:08:38Z · sase-1oi.1] Commentary tail is live: MuseCommentaryTail ticks from stream_json_lines on_tick, writes each accepted commentary message as its own live_reply.md chunk, records muse_session_id at launch, and falls back to terminal text when no deltas stream. Lazy-imported so TUI first-paint stays at 3538 modules under the 3539 cap. just fix clean; 50 targeted tests pass (commentary tail+stream, muse provider stream, utf8 decode, import budget, agy probe). sase tool run check 307a0c857ef60b738f085e57c3c933cd: 57728 passed, 6 failed — 4 KNOWN unrelated, agy probe flaked then passed on rerun, capacity_only scan fails identically on the clean stashed tree (noted as PROPOSED FOLLOW-UP). epic-symbols none.

## Dependencies

- **Blocks:** [sase-1oi.2](sase-1oi.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oi.3](sase-1oi.3.md) ○ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oi.1/README.md) | [sase-1oi.1](sase-1oi.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf9b9db`](https://github.com/sase-org/sase/commit/cf9b9dbf39737dfc7bf924bd9979b9f3273985b3) | feat(llm-provider): tail Muse session-log commentary into live\_reply.md | [sase-1oi.1](sase-1oi.1.md) | 2026-10-26 23:09:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oi.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oi.1/README.md

<!-- sase:referenced-by:end -->

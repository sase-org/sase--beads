# Bead: sase-1tz.2.1.10 — Find and fix the top cyclic-garbage producers and heap retainers

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.10` · **Size:** medium
**Created:** 2026-11-19 11:13:28 EST · **Closed:** 2026-11-19 17:32:47 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

heap_retainers: census the object types freed by idle full collections (up to 7M objects each) and the types retained across them. Fix up to the top three measured producers or retainers, and record allocated blocks, RSS, and collected counts before and after.

## Notes

[2026-11-19T22:31:24Z · sase-1tz.2.1.10] CENSUS (controlled, live athena data, this tree): retained-types census via repo top_types/known_cache_census tooling ranks TUI-owned domain retainers as NotificationPlusOne 12,052 live (0.58 MB), SkillUseEvent 11,365 live (0.55 MB, whole-file snapshot cache for project gh_sase-org__sase), Notification 5,234 live (store _LOAD_CACHE copy + caller clone copy). Production freed scale from tui_stalls.jsonl.1 (pre-gc_policy-fix): idle gen-2 n=2021 max-collected 7,223,134 p50 320,055; backstop n=13 max 6,353,108; rss_backstop n=71 max 1,889,385; no census rows in production logs (SASE_TUI_GC_CENSUS was off on the live TUI). Cycle-producer probe (30 churn cycles through skill-use + notification loader paths with gc disabled, then one DEBUG_SAVEALL full collect): 0 unreachable cycles - the loader paths are retainers, not cyclic-garbage producers; the 7M-object idle collections come from UI-loop churn, not these loaders.

[2026-11-19T22:31:36Z · sase-1tz.2.1.10] FIX 1/2 (sase-1tw demonstrated): deleted the whole-file _skill_uses_snapshot_cache (up to 8 projects x full event tuples) from src/sase/ace/tui/skill_uses.py. Per-agent and per-context loaders now issue one targeted newest-first scan (new query_skill_use_events in src/sase/skills/use_log.py, 5000-line scan budget, malformed-line tolerant) and keep only the capped per-agent result (50 x BoundedLRU 128). Matching semantics unchanged (artifacts-dir wins, agent-name fallback, newest-first, dedupe, limit). Cold miss on the live 11,365-line/5.6MB sase log: 0.268s -> 0.075s; retained SkillUseEvent 11,360 -> 0 (sparse) / <=50 per agent (hot tail agent 0.004s, 1 retained). Regression tests: unrelated-events-never-materialized retention test, scan-budget test, targeted-scan revalidation test, query unit tests (limit/scan-limit/missing-file). FIX 2/2 (observability): added sase.skills.use_log.SkillUseEvent to CENSUS_WATCHLIST and removed the dead skill_uses probe from known_cache_census; next census soak tracks the fixed type. sase tool run check: all gates pass except one symvision NEW on LaunchPromptContext (src/sase/axe/run_agent_runner_setup_prompt.py), verified byte-identical on clean HEAD worktree - pre-existing, recorded as follow-up.

[2026-11-19T22:31:52Z · sase-1tz.2.1.10] PROPOSED FOLLOW-UP: sase-1tw closure - SkillUseEvent whole-file retention is resolved on this tree (snapshot cache deleted, retention test test_unrelated_events_are_never_materialized proves unrelated events are never materialized); land agent may close sase-1tw citing this bead.

[2026-11-19T22:31:58Z · sase-1tz.2.1.10] PROPOSED FOLLOW-UP: sase-1tx TUI bound - store already caps +1 tails at 500/row (sase-core NOTIFICATION_PLUS_ONE_MAX_ENTRIES, overflow in plus_ones_dropped); remaining TUI work is a boundary compaction (keep latest K per row, fold remainder into plus_ones_dropped so plus_one_count stays truthful, hydrate full list for the selected modal row only). Needs a modal UX decision first; not made here.

[2026-11-19T22:32:04Z · sase-1tz.2.1.10] PROPOSED FOLLOW-UP: symvision NEW LaunchPromptContext in src/sase/axe/run_agent_runner_setup_prompt.py fails sase tool run check identically on clean HEAD 49b96a9c50 (separate worktree run) - pre-existing, not from this phase; needs owner triage.

[2026-11-19T22:32:09Z · sase-1tz.2.1.10] PROPOSED FOLLOW-UP: per-type freed census still missing - production tui_stalls logs carry collected counts but no census rows; run the next SASE_TUI_GC_CENSUS=1 soak (now tracking SkillUseEvent) to rank survivor types post-fix.

[2026-11-19T22:32:20Z · sase-1tz.2.1.10] AFTER-INSTALL REPEAT: (1) retained census: SASE_TUI_GC_CENSUS=1 soak, filter tui_stalls.jsonl census rows by app_instance_id, compare survivor_top/watch for SkillUseEvent/NotificationPlusOne vs this note; (2) freed scale: group tui_gc_pause generation==2 rows by trigger for collected max/p50; (3) loader micro-check: .venv/bin/python /tmp/sase-1tz.2.1.10-after2.py (kept as scratch probe); (4) tests: pytest tests/test_skill_use_log.py tests/ace/tui/test_skill_uses_loader.py tests/ace/tui/util/test_gc_policy_census.py.

[2026-11-19T22:32:47Z · sase-1tz.2.1.10] heap_retainers done and verified: (1) retained census ranks SkillUseEvent 11,365 and NotificationPlusOne 12,052 as top TUI-owned retainers; loader churn yields zero cyclic garbage (SAVEALL probe). (2) Deleted the whole-file _skill_uses_snapshot_cache; loaders use targeted newest-first scans (new query_skill_use_events) keeping <=50 events/agent - cold miss 0.268s->0.075s, retained 11,360->0. (3) CENSUS_WATCHLIST now tracks SkillUseEvent. Tests: 104 focused tests pass (loader, query, census, bounded-lru, header, skill-uses, macro cli_show); ruff+mypy clean; sase tool run check passes all gates except pre-existing symvision NEW on LaunchPromptContext, verified identical on clean HEAD worktree (recorded as follow-up). Metrics, repeat commands, and 4 follow-ups recorded as bead notes; evidence noted on sase-1nc; summary noted on sase-1tz.2.

## Dependencies

- **Blocks:** [sase-1tz.2.1.13](sase-1tz.2.1.13.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.9](sase-1tz.2.1.9.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.10/README.md) | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`225bfb7`](https://github.com/sase-org/sase/commit/225bfb7ff24084ad4ffe3e9ba962d6d8c478784a) | perf(tui): replace skill-use whole-file snapshot cache with targeted scans | [sase-1tz.2.1.10](sase-1tz.2.1.10.md) | 2026-11-19 17:34:31 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.2.1.10][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1tz.2.1.land][2] | verify heap_retainers phase recorded follow-ups and measurements | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.10/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.1.land.md

<!-- sase:referenced-by:end -->

# Bead: sase-135.7 — Prove the combined product and publish rerunnable evidence

[Bead Pages](../README.md) / [sase-135](README.md) / sase-135.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.7` · **Size:** medium
**Created:** 2026-09-18 22:19:25 EDT · **Closed:** 2026-09-20 10:33:03 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:074321e36a2c8946d4da94e1 | attached via sase artifact create --bead |
| related | file:explicit:0e89dc58cb70ea10e0c04265 | attached via sase artifact create --bead |
| related | file:explicit:1cdcdaba2c679af28aae4b72 | attached via sase artifact create --bead |
| related | file:explicit:520c398536d21fedf3bdf521 | attached via sase artifact create --bead |
| related | file:explicit:60cb7f4ab05a5ef935215e4c | attached via sase artifact create --bead |
| related | file:explicit:6bf5c7274eb71c01baf5d7f4 | attached via sase artifact create --bead |
| related | file:explicit:b5004922a60209e398ace728 | attached via sase artifact create --bead |
| related | file:explicit:e1f353dd187f8f1f5918a130 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

acceptance: Implement section 7 and the numbered Definition of Done. Run the real CLI harness and combined checks, dogfood check, arrange the final verify monitor handoff, and publish an evaluation artifact with exact commands, results, run identities, limitations, and ownership of unrelated failures.

## Notes

[2026-09-20T14:19:26Z · sase-135.7] PROPOSED FOLLOW-UP: persist ToolRun finish diagnostics in sase-core — canonical_event strips diagnostics and finish stores none, so a spawn error typed reason (executable not found / not executable), stage-ingest diagnostics and log-write facts are printed but not durable; this phase records log truncation as an output record in events.jsonl instead (logs.record_truncation).

[2026-09-20T14:19:54Z · sase-135.7] PROPOSED FOLLOW-UP: extend ToolRun retention to quarantined stores (runs.sqlite.corrupt-*) — the plan lists them under retention but core retention only selects log/event files and rows, so quarantined stores accumulate under tools/.

[2026-09-20T14:20:20Z · sase-135.7] PROPOSED FOLLOW-UP: tools/AGENTS.md (and its CLAUDE/GEMINI/OPENCODE/QWEN shims) still says later-phase harness cases are labeled phase-pending; the harness now labels live cases not-run and covers every DoD case — update the ToolRun smokes paragraph through /sase_memory_write (needs explicit user approval).

[2026-09-20T14:20:46Z · sase-135.7] PROPOSED FOLLOW-UP: tests/completion/test_zsh_smoke.py::test_alias_sbd_completes_static_bead_tree times out at its 5 s PTY read under host load (load 30-45 on 64 CPUs); it passes in isolation and on unmodified master, so it is a load-sensitive flake with no owner bead.

[2026-09-20T14:21:13Z · sase-135.7] PROPOSED FOLLOW-UP: print the wrapper header (sase tool run <id>) before a launch error — a spawn failure (127/126) settles a recorded run but never prints its id, so the user cannot run sase tool show on it.

[2026-09-20T14:21:39Z · sase-135.7] Baseline note for the land agent: sase-13m (tests/contract_manifest.txt missing test_tool_adoption_report_tool.py) is fixed by this phase by dropping that test contract marker (the manifest budget is 66 entries); just check is otherwise red on unmodified master at lint (mypy) sase-13k and lint (symvision) sase-13s, which stop check-full before its test stages.

[2026-09-20T14:32:24Z · sase-135.7--1] PROPOSED FOLLOW-UP: rerun `sase tool run check-full` under a verify monitor on a tree rebased onto origin/master 45df425498 or later — the monitored run a82428c6b5a0d2980c9ff35b3acd030e (monitor nfds30rc9fe5) stopped at lint (mypy) on base 86ff62c08a because sase-13k (now closed) was fixed upstream after that base; expect the next stop at lint (symvision), sase-13s; only a completed run with screenshot report and golden diff reviewed can turn DoD-13 to pass

[2026-09-20T14:33:03Z · sase-135.7--1] E1 phase 7 acceptance. Exhaustive check-full is INCOMPLETE (not green); every other DoD case is evidenced.
DEMO: workspace harness 35/35 pass with --live, 0 not-run (report file:explicit:1cdcdaba2c679af28aae4b72)
DEMO: installed sase 30/35 pass; the five failures are stale-deployment and exactly the behaviors this phase added (report file:explicit:074321e36a2c8946d4da94e1)
DEMO: pytest twin and E1 tests 96 passed (134.7 s); core just check passed on v0.34.67 plus the aggregate log_max_bytes retention change
DEMO: cold-start overhead median +0.151 s over sase proc list (target 0.5 s; 0.35 s before the observe.py import fix)
DEMO: monitor-owned check-full ToolRun a82428c6b5a0d2980c9ff35b3acd030e (owner monitor:nfds30rc9fe5, evidence complete, only events.jsonl, show -l delegates to the monitor log) settled failed/1 in 15.1 s at lint (mypy): recipe _lint-mypy failed on line 312, 20 [no-untyped-def] errors in src/sase/main/ace_tmux*.py; DoD-8 pass; DoD-13 stays not-run (exhaustive stages never ran)
Existing owners: sase-13k (mypy; now closed, fix 45df425498 is on origin/master but postdates tested base 86ff62c08a); next red lint (symvision) sase-13s (open). No screenshot stage ran: no latest-report.json, golden diff empty, no golden hand-edited.
Artifacts (v2 final): report file:explicit:e1f353dd187f8f1f5918a130, evidence file:explicit:6bf5c7274eb71c01baf5d7f4; supersede v1 file:explicit:520c398536d21fedf3bdf521 and file:explicit:60cb7f4ab05a5ef935215e4c.
epic-symbols: none for sase-135.7. PROPOSED FOLLOW-UP notes are recorded on this bead, including the check-full rerun on a tree rebased onto origin/master.

## Dependencies

- **Depends on:** [sase-135.6](sase-135.6.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-135.7.md) | [sase-135.7](sase-135.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`58f2de8`](https://github.com/sase-org/sase/commit/58f2de8f80e88754ca4905322855f463e3f0d840) | feat(tool): make ToolRun output truncation explicit and prove E1 end to end | [sase-135.7](sase-135.7.md) | 2026-09-20 10:34:36 EDT |
| sase-core | [`sase-core@1db3b29`](https://github.com/sase-org/sase-core/commit/1db3b298f5f1ff35148ba808802252dd7d225726) | feat(tool-run): apply the aggregate log\_max\_bytes retention target | [sase-135.7](sase-135.7.md) | 2026-09-20 10:37:53 EDT |

# Bead: sase-19i.5 — Keymap, action, docs, visual goldens, and bench

[Bead Pages](../README.md) / [sase-19i](README.md) / sase-19i.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s5.md) · **Assignee:** `sase-19i.5` · **Size:** medium
**Created:** 2026-09-25 13:06:14 EDT · **Closed:** 2026-09-25 23:38:12 EDT
**Plan:** [202609/agents\_node\_finder.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_finder.md)

## Description

finder-wiring: bind quotation_mark to jump_to_node on the Agents tab across the keymap validation, dataclass, default config, metadata, bindings, availability, command palette, help, docs, and module exports. Connect the modal's result to the jump ladder and drop the epic-symbol whitelist. Add end-to-end tests, PNG goldens, and the 2,000-node perf bench.

## Notes

[2026-09-26T02:09:40Z · sase-19i.5] PROPOSED FOLLOW-UP: Node Finder open misses 50ms budget at 2000 nodes (p50 ~154ms; snapshot ~140 + filter ~16 + Tier0 ~7) — needs snapshot/filter cost work, see bench_node_finder.py::test_bench_node_finder_open

[2026-09-26T02:09:56Z · sase-19i.5] PROPOSED FOLLOW-UP: Broad-query keystroke refilter blocks pump ~190ms at 2000 rows (filter 30 + row render 70 + OptionList churn) despite latest-wins coalescing — needs match-span reuse or list virtualization

[2026-09-26T02:41:45Z · sase-19i.5] PROPOSED FOLLOW-UP: Unified query predicates match-all on clan fixtures (status:RUNNING/tribe:epic/name:x -> all rows; only status:FAILED filters) and SASE_FEATURE_FLAGS env forces agents_unified_query=true so override_flags(agents_unified_query=False) is a no-op in tests

[2026-09-26T03:37:55Z · sase-19i.5--1] PROPOSED FOLLOW-UP: just test-scoped escalated to full lane: 6 failures + 70 collection errors reproduce identically on clean base tree (verified via git stash -u): test_agent_session_terminology (agent_family_parallel alias), test_contract_manifest marker selection, 4x test_run_agent_runner_wait_queue (queue_capacity_multiplier), AgentInfo.__new__ TypeError errors across test_axe_run_agent_* / test_run_agent_runner_* / test_run_agent_workspace_identity — unrelated to finder-wiring; touched-area tests 175/175 green

[2026-09-26T03:38:12Z · sase-19i.5--1] finder-wiring done: quotation_mark bound to jump_to_node across validation, AppKeymaps, default config, metadata, bindings, palette, availability, action, help, docs; 4 sase-19i epic-symbols removed; keymap/catalog/e2e tests, 6 PNG goldens, bench (keystroke/highlight PASS, open p50 154ms vs 50ms FAIL with follow-up noted); O(n2) row-guide render fixed, latest-wins refilter coalescing added; touched-area 175/175 green, epic-symbols clean; test-scoped full-lane failures (6 failed + 70 errors in axe run_agent/terminology/contract-manifest) reproduce identically on clean base tree, recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-19i.2](sase-19i.2.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-19i.4](sase-19i.4.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-19i.6](sase-19i.6.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.5.md) | [sase-19i.5](sase-19i.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`df0d58d`](https://github.com/sase-org/sase/commit/df0d58d337f06b8e20878ebc0734a6309041c647) | feat(agents-finder): wire quotation\_mark to jump\_to\_node with goldens and bench | [sase-19i.5](sase-19i.5.md) | 2026-09-25 23:45:37 EDT |

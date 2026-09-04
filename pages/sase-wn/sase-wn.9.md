# Bead: sase-wn.9 — Reuse sase-core release builds across workspaces

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.9` · **Size:** medium
**Created:** 2026-09-04 12:11:15 EDT · **Closed:** 2026-09-04 17:31:14 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

core-build-cache: add a host-level sase_core_rs wheel cache keyed by sase-core commit, toolchain, and ABI so ephemeral workspaces install a cached wheel instead of each running a multi-core-minute maturin release build; cache miss or dirty checkout falls back to today's build path.

## Notes

[2026-09-04T20:36:22Z · sase-wn.9] PROPOSED FOLLOW-UP: split oversized link_follow module — just check currently fails toobig because src/sase/ace/tui/actions/link_follow.py has 1066 lines over the 1000-line limit; this is unrelated to the core wheel cache phase.

[2026-09-04T21:21:13Z · sase-wn.9] PROPOSED FOLLOW-UP: investigate unrelated full-suite failures — `just test-scoped` escalated to the full suite after the Justfile change and failed tests/ace/tui/widgets/test_agent_list_runtime_rendering.py::test_format_agent_option_active_family_uses_nested_monitor_runtime (expected runtime suffix 2m/2m, got 2m/3m) and tests/ace/tui/test_proc_producer_inventory.py::test_inventory_records_infrastructure_and_classifications (expected 43 producers, got 42).

[2026-09-04T21:31:14Z · sase-wn.9] Implemented host sase-core wheel cache and Justfile rust-install integration. Verified focused cache/Justfile/manifest/shutdown pytest: 26 passed; just rust-install populated the cache, then a repeat run installed the cached wheel in 2.8s and skipped maturin develop; installed extension bytes matched the cached wheel. Passed fmt-py-check, fmt-md-check, _lint-mypy, _lint-pyscripts, _lint-symvision, and just validate. just check was run and is blocked by unrelated toobig failure in src/sase/ace/tui/actions/link_follow.py; escalated full test lane ran 38623 passed/19 skipped with two unrelated failures recorded as proposed follow-up.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.9/README.md) | [sase-wn.9](sase-wn.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da95c82`](https://github.com/sase-org/sase/commit/da95c82480b8ab258478fdd5eacdaf49abfd519c) | feat: cache sase-core release wheels | [sase-wn.9](sase-wn.9.md) | 2026-09-04 17:33:47 EDT |

# Bead: sase-tt.2 — Stop revalidating the agent-name registry on every load

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.2` · **Size:** medium
**Created:** 2026-08-25 14:59:12 EDT · **Closed:** 2026-08-25 16:24:14 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

registry: make the process-cached registry stop paying a full source-signature stat sweep and a full per-entry owner-existence sweep on every `load_name_registry()` call, which is 905ms of the Agent pane's 1529ms load.

## Notes

[2026-08-25T20:23:48Z · sase-tt.2--2] PROPOSED FOLLOW-UP: sase init memory --check fails on a clean master checkout (AGENTS.md/CLAUDE.md/GEMINI.md/QWEN.md/OPENCODE.md and sase/artifact_relations.json all report drift) -- pre-existing, unrelated to sase-tt.2, blocks just check SASE-validation gate for all agents until someone with memory-file approval runs sase memory init.

[2026-08-25T20:24:14Z · sase-tt.2--2] Verified registry TTL-memo change: pytest -m slow tests/perf/bench_agent_catalog.py passed after tightening _BUDGET_MS to 550.0; post-fix benchmark samples were ~158-169ms median and ~192-202ms max versus the old 900ms budget. just check was rerun: fmt and all lint gates passed, but the pre-existing unrelated SASE validation init memory --check drift in managed memory/provider files still fails on a clean checkout, so it was not regenerated without user approval. sase bead epic-symbols sase-tt.2 reported no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tt.2.md) | [sase-tt.2](sase-tt.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fe66394`](https://github.com/sase-org/sase/commit/fe663948fa8d495d3eda69d67a7dc7f0ae757f75) | perf(agent-names): memoize registry staleness checks | [sase-tt.2](sase-tt.2.md) | 2026-08-25 16:25:21 EDT |

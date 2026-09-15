# Bead: sase-117.1 — Deterministic repro harness

[Bead Pages](../README.md) / [sase-117](README.md) / sase-117.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l7.md) · **Assignee:** `sase-117.1` · **Size:** medium
**Created:** 2026-09-15 09:49:38 EDT · **Closed:** 2026-09-15 11:09:42 EDT
**Plan:** [202609/ace\_family\_status\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_family_status_convergence.md)

## Description

repro-harness: build a sandbox-home pytest harness that replays the recorded stale-family incident step by step through the real loader/merge/apply seams, pins the exact in-session pinning mechanism, and commits xfail tests plus a unit test for the exact-delta queue-loss defect.

## Notes

[2026-09-15T15:08:54Z · sase-117.1] PINPOINT: Phase 1 repro added tests/ace/tui/test_agent_family_status_convergence_repro.py. The exact-delta unit xfail pins _enqueue_agent_artifact_delta_paths dropping marker dirs when _dirty_agent_artifact_fallback_reason is already set. The incident replay xfail drives the real loader, prepared apply, artifact index, and agents surface token path: after a stale notification load accepts the agents token, a monitor-only index upsert is invisible to _probe_agents_token, and the first post-upsert bounded load still preserves the stale AgentType.WORKFLOW monitor over the settled AgentType.RUNNING EPIC CREATED row because merge keys include agent_type before dedup_running_vs_workflow drops the RUNNING row. Verification: .venv/bin/python -m pytest tests/ace/tui/test_agent_family_status_convergence_repro.py -q => 2 xfailed; tools/validate_sase_core_rs passed on linked core 0.34.35; just check passed static gates and validation but its core-identity escalated full-suite lane failed one unrelated machines-pane test that passed on direct rerun.

[2026-09-15T15:09:42Z · sase-117.1] Added tests/ace/tui/test_agent_family_status_convergence_repro.py with strict xfail coverage for exact-delta queue loss and the stale-family settlement replay. Verified .venv/bin/python -m pytest tests/ace/tui/test_agent_family_status_convergence_repro.py -q => 2 xfailed; tools/validate_sase_core_rs passed on linked core 0.34.35; just check passed static gates and SASE validation, then escalated to the broad fast suite and hit one unrelated machines-pane failure that passed on direct rerun. epic-symbols reported no entries for this phase.

## Dependencies

- **Blocks:** [sase-117.2](sase-117.2.md) ◐ · ⧖ 2026-09-15
- **Blocks:** [sase-117.3](sase-117.3.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-117.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-117.1/README.md) | [sase-117.1](sase-117.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f690e67`](https://github.com/sase-org/sase/commit/f690e6765a12b6fce283f405ed11633a5f0f80a2) | test(ace): add family status convergence repro | [sase-117.1](sase-117.1.md) | 2026-09-15 11:11:58 EDT |

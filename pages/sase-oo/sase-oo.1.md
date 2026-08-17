# Bead: sase-oo.1 — Correct the Rust statistics counters and expose breakdown truncation

[Bead Pages](../README.md) / [sase-oo](README.md) / sase-oo.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04y.md) · **Assignee:** `sase-oo.1` · **Size:** medium
**Created:** 2026-08-17 12:01:58 EDT · **Closed:** 2026-08-17 12:45:59 EDT
**Plan:** [202608/statistics\_tab\_accuracy\_round\_two.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_tab_accuracy_round_two.md)

## Description

core-counters: in ../sase-core, make `committing_agents` count distinct agent names and add `committing_runs`, stop counting a missing archive project spec as malformed, scope `user_hidden_skipped` to runner-eligible rows, add per-row xprompt breakdown truncation counts, bump the wire schema, and update the pinned version in this repo's core validator.

## Notes

[2026-08-17T16:20:33Z · sase-oo.1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-om — check_feature_flags rule 8 reports sase-om has no definition for key completion_refresh_on_update; unrelated to core-counters, left standing

[2026-08-17T16:45:59Z · sase-oo.1] Verified F3/F6/F7/F9 in sase-core: committing_agents is distinct agent names, committing_runs is the per-run count, missing archive specs are skipped not malformed, user_hidden_skipped is runner-eligible only, xprompt rows carry models/projects/partners_truncated, AGENT_STATS_WIRE_SCHEMA_VERSION is 6. sase-core just check passed; landed 02a37e9. Rebuilt the binding; validate_sase_core_rs and its contract tests pass. just check lint (feature flags) fails on unrelated live bead sase-om; remaining gates including the escalated scoped full suite passed.

[2026-08-17T16:47:35Z · sase-oo.1] Verified F3/F6/F7/F9 in sase-core: committing_agents is distinct agent names, committing_runs is the per-run count, missing archive specs are skipped not malformed, user_hidden_skipped is runner-eligible only, xprompt rows carry models/projects/partners_truncated, AGENT_STATS_WIRE_SCHEMA_VERSION is 6. sase-core just check passed; landed 02a37e9. Rebuilt the binding; validate_sase_core_rs and its contract tests pass. just check lint (feature flags) fails on unrelated live bead sase-om; remaining gates including the escalated scoped full suite passed.

## Dependencies

- **Blocks:** [sase-oo.4](sase-oo.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oo.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oo.1/README.md) | [sase-oo.1](sase-oo.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@02a37e9`](https://github.com/sase-org/sase-core/commit/02a37e9d283a02cbf6bcbc95bea0df959f6b72c6) | fix(agent\_stats): correct commit, spec, runner, and xprompt counters | [sase-oo.1](sase-oo.1.md) | 2026-08-17 12:35:36 EDT |
| sase | [`24936ff`](https://github.com/sase-org/sase/commit/24936ffee3fc5136ed10bc9226bd63f8d9c4a869) | fix(core): require agent-stats schema 6 and truncation fields | [sase-oo.1](sase-oo.1.md) | 2026-08-17 12:48:23 EDT |

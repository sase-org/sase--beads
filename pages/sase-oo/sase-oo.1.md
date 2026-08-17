# Bead: sase-oo.1 — Correct the Rust statistics counters and expose breakdown truncation

[Bead Pages](../README.md) / [sase-oo](README.md) / sase-oo.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04y.md) · **Assignee:** `sase-oo.1` · **Size:** medium
**Created:** 2026-08-17 12:01:58 EDT
**Plan:** [202608/statistics\_tab\_accuracy\_round\_two.md](https://github.com/sase-org/sase--plans/blob/main/202608/statistics_tab_accuracy_round_two.md)

## Description

core-counters: in ../sase-core, make `committing_agents` count distinct agent names and add `committing_runs`, stop counting a missing archive project spec as malformed, scope `user_hidden_skipped` to runner-eligible rows, add per-row xprompt breakdown truncation counts, bump the wire schema, and update the pinned version in this repo's core validator.

## Notes

[2026-08-17T16:20:33Z · sase-oo.1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails on live flag bead sase-om — check_feature_flags rule 8 reports sase-om has no definition for key completion_refresh_on_update; unrelated to core-counters, left standing

## Dependencies

- **Blocks:** [sase-oo.4](sase-oo.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-oo.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-oo.1/README.md) | [sase-oo.1](sase-oo.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@02a37e9`](https://github.com/sase-org/sase-core/commit/02a37e9d283a02cbf6bcbc95bea0df959f6b72c6) | fix(agent\_stats): correct commit, spec, runner, and xprompt counters | [sase-oo.1](sase-oo.1.md) | 2026-08-17 12:35:36 EDT |

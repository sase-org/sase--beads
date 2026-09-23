# Bead: sase-177.3 — Tool-call capture for Muse's legacy shell tool

[Bead Pages](../README.md) / [sase-177](README.md) / sase-177.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qc--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qc.md) · **Assignee:** `sase-177.3` · **Size:** small
**Created:** 2026-09-23 17:47:10 EDT · **Closed:** 2026-09-23 18:05:01 EDT
**Plan:** [202609/muse\_single\_turn\_normalization.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_single_turn_normalization.md)

## Description

muse-shell-tool-calls: capture a real muse exec --enable-shell-tool fixture, display `shell` calls as Bash with the best command target the stream allows, and record a timed-out tool result as a failure instead of a success; tests and docs.

## Notes

[2026-09-23T22:04:05Z · sase-177.3] PROPOSED FOLLOW-UP: just check validate gate fails on stale home memory (init memory --check wants to refresh ~/.local/share/chezmoi/home SASE memory/shims); unrelated to muse-shell-tool-calls diff, reproduce with sase init memory --check on a clean tree

[2026-09-23T22:05:01Z · sase-177.3] shell fixture muse_exec_shell_tool_R3401.1.jsonl captured live (muse-spark-1.3, echo + nonzero exit); shell displays as Bash with honest preview target; timeout/timed_out map to failure; 20/20 artifact tests and 1160/1160 tests/llm_provider pass, ruff clean; just check validate blocked by pre-existing home-memory drift (noted as follow-up)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-177.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.3/README.md) | [sase-177.3](sase-177.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0368d5`](https://github.com/sase-org/sase/commit/a0368d54f1fb99e55bb261b785b67751777544a8) | feat(llm-provider): capture Muse shell tool calls and map timeout outcomes to failure | [sase-177.3](sase-177.3.md) | 2026-09-23 18:07:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-177.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.3/README.md

<!-- sase:referenced-by:end -->

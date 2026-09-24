# Bead: sase-17m.2.1.2 — Scan, runtime, lifecycle, runner, and stats wires

[Bead Pages](../README.md) / [sase-17m.2.1](sase-17m.2.1.md) / sase-17m.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.2.md) · **Assignee:** `sase-17m.2.1.2` · **Size:** medium
**Created:** 2026-09-23 22:54:51 EDT · **Closed:** 2026-09-24 01:00:48 EDT
**Plan:** [202609/agent\_session\_core\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_core_expand.md)

## Description

scan-runtime: rename the family concept in agent_scan, agent_runtime, agent_clan_record, agent_cleanup, agent_ownership, agent_group_archive, agent_stats, runner_capacity, gate_followup, and their neighbours. Pin legacy serde spellings, read new-then-legacy keys in hand-read JSON, and add the reconcile_agent_artifact_index_dismissed_agent_session_members binding.

## Notes

[2026-09-24T04:48:20Z · sase-17m.2.1.2] PROPOSED FOLLOW-UP: wire-cutover switches sase callers to the new core spellings (convert_session op, agent_session_generation keys, reconcile_agent_artifact_index_dismissed_agent_session_members binding) and tightens dual-shape tests; core renamed missing_family_member_name/family_conversion_upsert codes (sase has no match on them)

[2026-09-24T04:48:53Z · sase-17m.2.1.2] PROPOSED FOLLOW-UP: core-contract flips/removes legacy pins from this phase — agent_scan/wire.rs agent_family+role+parallel/family_shell keys, lineage result family_root_dismissed, candidates/storage AGENT_SESSION_INDEX_COLUMN, ownership family_generation/expected_family_generation/convert_family/CONTAINER+RESERVATION_KIND values, runner_capacity record keys + serial_family claim kind, cleanup agent_family_parallel, group canonical_global_family, gate followup family_name, stats group-by family, reconcile_..._dismissed_family_members binding

[2026-09-24T04:49:23Z · sase-17m.2.1.2] PROPOSED FOLLOW-UP: flake watch — tool_run::store::tests::private_argv_is_not_serialized_on_queries failed once under the full parallel lane and passes alone; no tool_run files touched this phase, no flake bead filed

[2026-09-24T04:49:59Z · sase-17m.2.1.2] Exit record: remaining famil hits in phase scope are (a) unrelated meanings — artifact_file prefix/family matching + family.researcher fixture, provider_usage/model/query/glossary hits untouched; (b) legacy spellings pinned for core-contract — SQLite agent_family column+index, all serde rename targets, SERIAL_AGENT_SESSION_CLAIM_KIND=serial_family emission, PARALLEL_AGENT_SESSION_STILL_ACTIVE_DETAIL message (mirrors sase Python wording), ownership RESERVATION/CONTAINER_KIND values + session alias; (c) legacy binding reconcile_..._dismissed_family_members; (d) legacy-input fixtures + sase-side family prose (launch_validation, relaunch prompts, plan_chain) left for sase phases

[2026-09-24T05:00:48Z · sase-17m.2.1.2] scan-runtime complete: agent-session rename across agent_scan/scanner+wire+index, agent_runtime, agent_clan_record, agent_stats, runner_capacity, agent_ownership, agent_cleanup, agent_group_archive, gate_followup (+compiler-forced fleet/gateway caller updates); legacy serde spellings pinned, new-then-legacy hand-reads, new reconcile_..._agent_session_members binding beside legacy; verified by green sase tool run check in sase-core (just fast/clippy/fmt/tests/parity/gateway all pass; two unrelated parallel-lane flakes pass alone)

## Dependencies

- **Depends on:** [sase-17m.2.1.1](sase-17m.2.1.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-17m.2.1.3](sase-17m.2.1.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.2/README.md) | [sase-17m.2.1.2](sase-17m.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ef82848`](https://github.com/sase-org/sase-core/commit/ef8284804ab894ed8f3277726bea1e4cc34a6864) | feat(core): additive agent-session rename for scan, runtime, lifecycle, runner, and stats wires | [sase-17m.2.1.2](sase-17m.2.1.2.md) | 2026-09-24 01:01:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.2.1.2][1] | confirm phase bead closed after land | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.2.1.2/README.md

<!-- sase:referenced-by:end -->

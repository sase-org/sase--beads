# Bead: sase-1pt.1 — Stop the fenced Referenced By loop and carry prompt citations as link events

[Bead Pages](../README.md) / [sase-1pt](README.md) / sase-1pt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15z.md) · **Assignee:** `sase-1pt.1` · **Size:** medium
**Created:** 2026-10-29 18:11:06 EDT · **Closed:** 2026-10-29 21:46:22 EDT
**Plan:** [202610/commit\_stage\_async\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202610/commit_stage_async_publication.md)

## Description

refby-events: check the link-v2 fence before the lock, pull, and snapshot, emit prompt cites rows as publishable link events in fenced projects, make referenced-by failures charge attempts, and handle the existing queued backlog.

## Notes

[2026-10-30T01:46:07Z · sase-1pt.1] PROPOSED FOLLOW-UP: sase tool run check aa7e755e80302ed0e3f3a01a4b57d553 verdict no_new_failures (2 KNOWN: test_contract_manifest_matches_marker_selection stale manifest; test_commit_only_handoffs_keep_dirty_submission_required missing gate_schema_version; 1 FLAKY: test_commit_only_handoff_uses_one_shot_declaration_recovery same staged-handoff error) — witness 38949908dcddd9fda047dc0f9da17790; none from refby-events

[2026-10-30T01:46:22Z · sase-1pt.1] Fenced Referenced By never locks/pulls: drain converts backlog as migrated cites events (ack after append); unfenced refresh exceptions charge attempts and quarantine. Prompt cites emit as link-outbox events (commit identity via SASE_AGENT_TIMESTAMP, planner via sase/machine). Tests: fence skip, backlog convert, drain+drop_stale_terminal, projection match, trusted prompt_ref. just fix + lint green; sase tool run check aa7e755e no_new_failures (KNOWN/FLAKY only). No leftover --epic-symbol for sase-1pt.1.

## Dependencies

- **Blocks:** [sase-1pt.5](sase-1pt.5.md) ✓ · ⧖ 2026-10-29
- **Blocks:** [sase-1pt.6](sase-1pt.6.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.1/README.md) | [sase-1pt.1](sase-1pt.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5f675c3`](https://github.com/sase-org/sase/commit/5f675c311f82fa66c82ff8659daa7f246da62f44) | feat(artifact-links): emit fenced prompt cites as link events | [sase-1pt.1](sase-1pt.1.md) | 2026-10-29 22:46:48 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pt.1][1] | Need the phase scope, design file, notes, and whether earlier work landed | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.1/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-19i.7.3.1 — Bound snapshot construction for first paint

[Bead Pages](../README.md) / [sase-19i.7.3](sase-19i.7.3.md) / sase-19i.7.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.land.md) · **Assignee:** `sase-19i.7.3.1` · **Size:** medium
**Created:** 2026-09-26 10:26:46 EDT · **Closed:** 2026-09-26 10:46:58 EDT
**Plan:** [202609/node\_finder\_remaining\_budgets.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_remaining_budgets.md)

## Description

snapshot-facets: profile and fuse repeated per-agent snapshot work while preserving every reachable row and hidden reason.

## Notes

[2026-09-26T14:46:10Z · sase-19i.7.3.1] PROPOSED FOLLOW-UP: just check symvision gate fails on three stale sase-19x.4 --epic-symbol entries (phase_card_block, block_meta_for_session_shell, session_reply_heading); reproduces identically on clean base tree; owned by active epic sase-19x

[2026-09-26T14:46:22Z · sase-19i.7.3.1] PROPOSED FOLLOW-UP: sase tool run check refuses with tools.check wire error (unknown field receipt in sase/sase.yml); verification fell back to SASE_TOOL_BYPASS just check; remedy likely sase update

[2026-09-26T14:46:42Z · sase-19i.7.3.1] snapshot-facets done: fused per-agent facets (parent/fold keys, depth, identity, hidden-step) into one per-open pass in _node_finder_snapshot._snapshot_facets reused across fold-filter check, levels fill, row construction, and omission walk; grouping_keys_for now reads _grouping_name once per agent instead of 4x. Snapshot-only on 2000-node bench harness (25 post-warmup): BEFORE p50 102.5ms p95 217.0ms min 72.0 max 229.4; AFTER p50 89.2ms p95 195.0ms min 75.2 max 200.2 (loaded host, high variance). Remaining pre-mount cost for modal-budget: build_agent_tree runs twice per open (snapshot panel trees over expanded roster plus _jump_candidate_targets trees over live _agents with same mode+registry), ~6 presentation_anchor_lookup builds per open across snapshot/jump/panel paths, per-row describe_node_finder_row plan-chain predicates, header ancestor chains. Focused suites green: 73 passed (snapshot/modal/model/preview/e2e/grouping); new cross-mode regression test locks identical node sets, reasons, unmet counts, and header counts across STANDARD/BY_DATE/BY_STATUS/BY_MACHINE. ruff+format+mypy clean. just check green except pre-existing sase-19x.4 symvision staleness verified identical on clean base (recorded as follow-up). No rendered-output change so no visual snapshots.

[2026-09-26T14:46:58Z · sase-19i.7.3.1] Fused per-open snapshot facets + single-read grouping keys; 73 focused tests pass, ruff/mypy clean, new cross-mode regression locks counts/reasons/headers; snapshot-only p50 102.5->89.2ms on 2000-node harness; just check green except pre-existing sase-19x.4 symvision failure verified identical on clean base

## Dependencies

- **Blocks:** [sase-19i.7.3.2](sase-19i.7.3.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.1/README.md) | [sase-19i.7.3.1](sase-19i.7.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d1b72cf`](https://github.com/sase-org/sase/commit/d1b72cfe58e815deafe4e7c72c4774b487346efd) | feat(ace): fuse per-open Node Finder snapshot facets (sase-19i.7.3.1) | [sase-19i.7.3.1](sase-19i.7.3.1.md) | 2026-09-26 10:49:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-19i.7.3.2][2] | Need prior phase profile findings for modal-budget handoff | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.2/README.md

<!-- sase:referenced-by:end -->

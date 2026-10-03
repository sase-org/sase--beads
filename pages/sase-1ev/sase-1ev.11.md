# Bead: sase-1ev.11 — Core review watermark and the CLI feed header

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.11` · **Size:** medium
**Created:** 2026-10-02 14:43:19 EDT · **Closed:** 2026-10-02 22:48:52 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

watermark-core: add a sase-core per-scope review watermark that is shared across workspace clones and only marked explicitly, plus its bindings and N-new semantics. sase memory history feed output shows N new since you last reviewed, and -m/--mark-reviewed advances it.

## Notes

[2026-10-03T02:48:32Z · sase-1ev.11] PROPOSED FOLLOW-UP: pre-existing check failures reproduce identically on clean base (verified via stash): just _lint-flags rule 7 closed flag bead sase-1ev still has surviving three_pane_splits definition (see also sase-1eu.8); symvision flags unused PublicationPayloadFile and plan_publication_payload_batches in publication_payload_facade.py; tests/completion/test_candidates_project_providers.py::test_bead_candidates_without_a_store_returns_empty_list and test_candidates_resource_providers.py::test_plan_candidates_emit_canonical_references fail — none touch memory history

[2026-10-03T02:48:52Z · sase-1ev.11] watermark-core done: sase-core review store ({state_dir}/memory_history_review.json, lock+rename writes, corrupt reads as empty+reported) with review_state/mark_reviewed queries and bindings; Python facade + HistoryService methods; CLI feed header per scope in text and pager formats, -m advances shown scopes, error with selectors, JSON wire unchanged. Verified: core sase tool run check succeeded (9 new core tests + binding round-trip); sase targeted suites 286+31+56 pass; ruff/mypy/keep-sorted/pyscripts/test-waits/changelog/terminology/toobig pass; cross-clone sharing and restart persistence verified live; 3 unrelated failures reproduce on clean base and are filed as PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-1ev.10](sase-1ev.10.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.12](sase-1ev.12.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.11/README.md) | [sase-1ev.11](sase-1ev.11.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c2a415e`](https://github.com/sase-org/sase-core/commit/c2a415e50d8353fc01bc14aaa3949e20326432e2) | feat(memory-history): add review state store with query and mark-reviewed | [sase-1ev.11](sase-1ev.11.md) | 2026-10-02 22:50:42 EDT |
| sase | [`a582a42`](https://github.com/sase-org/sase/commit/a582a422eb61df9bfe6d0480d37e3cb262f5c693) | feat(memory-history): add review watermark and CLI feed header with mark-reviewed | [sase-1ev.11](sase-1ev.11.md) | 2026-10-02 22:55:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ev.11][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.11/README.md

<!-- sase:referenced-by:end -->

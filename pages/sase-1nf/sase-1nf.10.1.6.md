# Bead: sase-1nf.10.1.6 — Expose bounded retries without full reconciliation

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.6` · **Size:** medium
**Created:** 2026-10-20 15:40:52 EDT · **Closed:** 2026-10-20 23:04:54 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

bounded-cli: add retry limit and error-class options, use Rust selection under the outbox lock, drain only the bounded request set, and document queue isolation and resume behavior.

## Notes

[2026-10-21T03:04:44Z · sase-1nf.10.1.6] PROPOSED FOLLOW-UP: investigate tests/test_commit_publication_inline.py::test_tagged_commit_publishes_and_pushes_every_sidecar_before_returning, which again fails with the deferred prompt-archive unresolved error (ToolRun 30dae056d0a760433ba607bdc54caef8); identical clean-HEAD reproduction is recorded in sase-1nf.10.1.4 note #2 (ToolRun 92f2d6a7b24fc900b7acbc9105c3f352, touched=false), related closed task sase-fi, and no active owner bead was found.

[2026-10-21T03:04:54Z · sase-1nf.10.1.6] Implemented bounded targeted publication retries with repeatable error-class filters, atomic outbox selection/revival, exact-key draining, CLI validation, completion metadata, docs, and tests. Focused retry/outbox/publication/completion tests pass; just check had 13,603 passed and 10 skipped with one reproduced clean-base prompt-archive failure, recorded as a PROPOSED FOLLOW-UP. git diff --check passes; epic-symbol check found no leftovers.

## Dependencies

- **Depends on:** [sase-1nf.10.1.5](sase-1nf.10.1.5.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.8](sase-1nf.10.1.8.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.6/README.md) | [sase-1nf.10.1.6](sase-1nf.10.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7a08bf2`](https://github.com/sase-org/sase/commit/7a08bf2fda1afae8950d04730092fd27df847092) | feat(agents-sync): expose bounded publication retries | [sase-1nf.10.1.6](sase-1nf.10.1.6.md) | 2026-10-20 23:05:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.6][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.6/README.md

<!-- sase:referenced-by:end -->

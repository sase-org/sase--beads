# Bead: sase-1h8.7 — One store read per CLI command

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.7` · **Size:** medium
**Created:** 2026-10-06 18:59:37 EDT · **Closed:** 2026-10-07 10:17:53 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Previously Closed

> ↺ Closed 2026-10-07T03:53:27Z · done
>
> (none)
>
> Reopened 2026-10-07T11:59:11Z by a status update

## Description

one-replay: route targets without a full read, resolve inside the locked mutation load, and collapse the Python lanes' redundant resolve/show calls so each command reads the store once.

## Notes

[2026-10-07T03:22:57Z · sase-1h8.7--1] After one-replay read counts (tests/test_bead/test_cli_store_read_counts.py, 11 passed): update 1, update --note 3, close 2, close --note 2, note 2, note --remove 2, create --parent 1, open 1, dep add 1, dep rm 1, rm 1. Routing (bead_route_targets) and target probing (bead_probe_target_owner) never load the store and are excluded from the counts.

[2026-10-07T03:53:06Z · sase-1h8.7--2] This turn fixed forward 9 check failures: (1) operation_context lazy registry read restores local-first (routing acceptance + operation_context tests), (2) removed premature Rust-verb gate in bead_fast_path (fast-path guard + attach +1 tests), (3) update --note dedup by resolved ID with per-input echo expansion (bulk timestamp test), (4) updated 4 stale delegation assertions to in-mutation resolution per phase design (show x2, remove_many, update_many). read_counts 11 passed; focused bead suites 92 passed; fmt/ruff/mypy clean. grok Enterprise probe + ace overlapping-checkouts flakes pass in isolation.

[2026-10-07T03:53:27Z · sase-1h8.7--2] One-replay verified: read_counts 11 passed (update 1, update -n 3, close 2, close --note 2, note 2, note --remove 2, create --parent 1, open 1, dep add 1, dep rm 1, rm 1); focused suites 92 passed (routing, operation_context, fast_path, attach, bulk, delegation); fmt/ruff/mypy clean; epic-symbols empty. Prior full check had 9 bead failures now fixed forward plus 2 load flakes (grok probe, ace checkout overlap) that pass in isolation.

[2026-10-07T14:03:32Z · sase-1h8.7] PROPOSED FOLLOW-UP: Commit sase-core dirty one-replay fixes (create.rs parent existence check, notes_update.rs requested_issue_ids on update path) then re-ratchet sase-core-revision.txt past that commit and rebuild; pin now at 91e0e49c covers bff4860c only, so CI built from pin lacks the two fixes golden create_missing_parent and update request-order tests need

[2026-10-07T14:08:03Z · sase-1h8.7] PROPOSED FOLLOW-UP: symvision _runs private-import violations in agents_sync/v2_snapshot_io.py and ace decks overview_card.py fail identically on clean base cf88fd924f (verified via worktree diff); owner bead to triage, do not hold one-replay for it

[2026-10-07T14:17:53Z · sase-1h8.7] One-replay verified: read-counts 13 passed (update 1, update-note 3, close 2, close-note 2, note 2, note-remove 2, create-parent 1, open 1, dep-add 1, dep-rm 1, rm 1, ref-add/rm 1); full tests/test_bead 2673 passed; ruff/mypy/fmt clean; pin ratcheted 4b4a0527 to 91e0e49c covering bff4860c; symvision _runs failure byte-identical on clean base, filed as follow-up

## Dependencies

- **Blocks:** [sase-1h8.11](sase-1h8.11.md) ◐ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.12](sase-1h8.12.md) ◐ · ⧖ 2026-10-06
- **Depends on:** [sase-1h8.4](sase-1h8.4.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.7/README.md) | [sase-1h8.7](sase-1h8.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bff4860`](https://github.com/sase-org/sase-core/commit/bff4860c273afc0270248c6eeb203dddda466435) | feat(bead): one-replay core support for in-mutation resolution and target probing | [sase-1h8.7](sase-1h8.7.md) | 2026-10-07 00:01:34 EDT |
| sase-core | [`sase-core@26ec2d6`](https://github.com/sase-org/sase-core/commit/26ec2d61d9c60eede1596ae7d8c897e74dfb8141) | feat(bead): report update request-order IDs and enforce create parent (sase-1h8.7) | [sase-1h8.7](sase-1h8.7.md) | 2026-10-07 10:19:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.7][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1h8.7--2][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.7.md

<!-- sase:referenced-by:end -->

# Bead: sase-1ck.9 — Purge, doctor, cache pruning, and bead pages

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.9` · **Size:** medium
**Created:** 2026-09-29 08:13:47 EDT · **Closed:** 2026-09-29 22:06:39 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

lifecycle: add tombstone-based attachment purge, bead doctor attachment checks and repairs, and cache/orphan pruning, and render private attachments on bead pages.

## Notes

[2026-09-30T02:05:37Z · sase-1ck.9] PROPOSED FOLLOW-UP: just check patch/stitch terminology gate fails identically on the clean base tree (14 defects, all in linked sase-core fixture crates/sase_core/tests/fixtures/note_attachment/at_bearing_notes.jsonl); needs a fixture allowlist or token fix outside this phase

[2026-09-30T02:05:58Z · sase-1ck.9] PROPOSED FOLLOW-UP: symvision flags pre-existing private import _kitty_graphics_support (show_images.py imports it from doctor/checks_deep_terminal.py); fails identically on base, out of lifecycle scope

[2026-09-30T02:06:09Z · sase-1ck.9] PROPOSED FOLLOW-UP: just validate asks to create the attachments-private sidecar in environments without one (fails identically on base); consider documenting the user-side sase repo init step from shared_store

[2026-09-30T02:06:20Z · sase-1ck.9] PROPOSED FOLLOW-UP: docs/cli.md attachment path row still says never fetches but shared_store made path always fetch; reconcile the row

[2026-09-30T02:06:39Z · sase-1ck.9] Lifecycle done: purge (tombstones to git+rclone+local, local removal, (purged) rendering, filter-repo procedure print, no event changes), bead doctor attachments section with -T/--fix-attachments repair (mismatches, dangling, pending, local-only, tombstoned, corrupt, 7d orphans; repairs remove/drain/quarantine), prune (dry-run default, budget bead.attachments.local_cache_max_bytes 10GiB, never evicts pending/local-only), bead pages Attachments section with private-only lines. Verified: 14 new lifecycle tests pass; neighboring suites green (96+109+60); ruff/mypy/fmt/toobig clean; no epic-symbols. Pre-existing base failures recorded as PROPOSED FOLLOW-UP (patch/stitch fixture defects, symvision kitty import, validate sidecar).

## Dependencies

- **Blocks:** [sase-1ck.10](sase-1ck.10.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.6](sase-1ck.6.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.9/README.md) | [sase-1ck.9](sase-1ck.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ee1620e`](https://github.com/sase-org/sase/commit/ee1620e1b919fb73d350b02767ecf81ab0577afc) | feat(bead): implement attachment lifecycle (purge, doctor, prune, pages) | [sase-1ck.9](sase-1ck.9.md) | 2026-09-29 22:10:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ck.9][1] | Need full description and notes for phase work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.9/README.md

<!-- sase:referenced-by:end -->

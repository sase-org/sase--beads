# Bead: sase-1h8.5 — Store fingerprint binding and consumer migration

[Bead Pages](../README.md) / [sase-1h8](README.md) / sase-1h8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.3u.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.3u.linker.w0.md) · **Assignee:** `sase-1h8.5` · **Size:** medium
**Created:** 2026-10-06 18:59:35 EDT · **Closed:** 2026-10-06 19:49:15 EDT
**Plan:** [202610/bead\_store\_history\_independent\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/bead_store_history_independent_performance.md)

## Description

fingerprint: add an exact stat-only bead_store_fingerprint core binding and move the five issues.jsonl mtime-keyed consumers onto it.

## Notes

[2026-10-06T23:38:23Z · sase-1h8.5] fingerprint phase audit: issues.jsonl content readers left for projection-off: core/artifact_file_protection.py (P3 protect path), bead/conflict_resolver_store_writer.py + conflict_resolver_paths.py, llm_provider/commit_finalizer_git_autocommit.py + finalizers/reconciliation_auto_commit.py, bead/cli_admin.py --fix-projection, core/health.py, bead/_sync_git.py + _project_store.py, main/parser_bead_store.py, bead/jsonl.py + ids.py + note/close_history/snooze/_db codecs + _project_mutations_lifecycle.py, tools/check_bead_note_migration + check_bead_store_soak, sdd/templates/sidecar-beads-README.md, config/sase.schema.json text, init_memory beads template, sdd/_store_maintenance.py stale ~5MB comment. Migrated to fingerprint here: artifact-ref catalog, wait-bead catalog, beads store key, plans store key, patches surface token (each keeps a legacy mtime fallback for pre-binding cores).

[2026-10-06T23:48:57Z · sase-1h8.5--1] PROPOSED FOLLOW-UP: just check lint-symvision fails identically on clean base tree (private _runs imported in src/sase/agents_sync/v2_snapshot_io.py and src/sase/ace/tui/widgets/decks/final/overview_card.py); pre-existing, unrelated to fingerprint phase

[2026-10-06T23:49:15Z · sase-1h8.5--1] fingerprint phase done: new bead_store_fingerprint core binding (sase-core fingerprint.rs + py binding, exposed as sase_core_rs.bead_store_fingerprint) with legacy mtime fallback; 5 consumers migrated (artifact-ref catalog, wait-bead catalog, beads store key, plans store key, patches surface token). Verified: 60 phase tests green incl. new test_bead_store_fingerprint_keys.py (projection-rewrite stability), ruff clean on touched files, all just-check gates green except pre-existing symvision _runs failure that reproduces identically on clean base (recorded as PROPOSED FOLLOW-UP). sase-core rust build green via just install; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1h8.11](sase-1h8.11.md) ◐ · ⧖ 2026-10-06
- **Blocks:** [sase-1h8.6](sase-1h8.6.md) ✓ · ⧖ 2026-10-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.5.md) | [sase-1h8.5](sase-1h8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7af3a73`](https://github.com/sase-org/sase-core/commit/7af3a73a427aa248a7e5021fb146160b55a97735) | feat(bead-store): add bead\_store\_fingerprint core binding with stat-only exact key | [sase-1h8.5](sase-1h8.5.md) | 2026-10-06 19:50:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.5--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1h8.5.md

<!-- sase:referenced-by:end -->

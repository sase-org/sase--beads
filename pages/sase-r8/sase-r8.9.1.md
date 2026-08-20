# Bead: sase-r8.9.1 — Publish the bead-link mutation bindings

[Bead Pages](../README.md) / [sase-r8.9](sase-r8.9.md) / sase-r8.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-r8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r8.land.md) · **Assignee:** `sase-r8.9.1` · **Size:** small
**Created:** 2026-08-20 09:42:21 EDT · **Closed:** 2026-08-20 10:36:28 EDT
**Plan:** [202608/artifact\_link\_core\_release.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_core_release.md)

## Description

core_release: release the linked sase-core commit containing bead_add_link and bead_remove_link inside the existing 0.29 compatibility window, and verify the published Python package exposes both bindings.

## Notes

[2026-08-20T13:55:34Z · sase-r8.9.1] Clippy too_many_arguments on py_bead_add_link blocked release PR #151; landed allow on sase-core master as b2568ee (on top of 751d60f). Waiting for release-plz to merge v0.29.5 and publish sase-core-rs with bead_add_link and bead_remove_link.

[2026-08-20T14:36:28Z · sase-r8.9.1--1] Verified GitHub tag/release v0.29.5 (PR #151 merged at f0bc8f0) contains 751d60f (bead_add_link/bead_remove_link) and b2568ee (clippy allow). PyPI sase-core-rs==0.29.5 is latest in the 0.29 window and independent wheel probe confirmed bead_add_link, bead_remove_link, plus 0.29.3 artifact-link APIs (artifact_link_row_schema_version, artifact_link_canonicalize, artifact_link_validate_row, artifact_link_upsert_row, links_block_parse, links_block_render). epic-symbols for this phase is empty; did not bump sase pyproject.toml/uv.lock (sase-r8.9.2).

## Dependencies

- **Blocks:** [sase-r8.9.2](sase-r8.9.2.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-r8.9.1.md) | [sase-r8.9.1](sase-r8.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b2568ee`](https://github.com/sase-org/sase-core/commit/b2568ee5849765be7fd86ad985137f22ba84749a) | fix(bead): allow clippy::too\_many\_arguments on bead\_add\_link | [sase-r8.9.1](sase-r8.9.1.md) | 2026-08-20 09:52:00 EDT |

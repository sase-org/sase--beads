# Bead: sase-ru.1 — Retire the mature formatter and plugin catalog paths

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.1` · **Size:** medium
**Created:** 2026-08-21 10:44:25 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

fast_retirements: verify and retire prettier_enabled and plugin_catalog_scoped_latest, including compatibility cleanup, schema synchronization, focused coverage, and bead closure.

## Notes

[2026-08-21T15:13:19Z · sase-ru.1] PROPOSED FOLLOW-UP: live flag bead sase-rc (artifact_links) has no registry definition and fails tools/check_feature_flags rule 8 — owned by the excluded artifact_links work; this phase did not touch it.

[2026-08-21T15:26:10Z · sase-ru.1] PROGRESS: prettier_enabled and plugin_catalog_scoped_latest retired; sase-qf and sase-qq closed. just check lint fmt/ruff/mypy green. tools/check_feature_flags --static green; full checker still errors on unrelated live orphan sase-rc (artifact_links). just test-scoped escalated (directory-conftest + src-data-asset + core-identity-changed). Focused tests passed (254 unit/CLI + 137 ACE). just plugin-catalog-scale-check passed. Next: just test && just test-visual, then close this phase.

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ru.1.md) | [sase-ru.1](sase-ru.1.md) | 0 |

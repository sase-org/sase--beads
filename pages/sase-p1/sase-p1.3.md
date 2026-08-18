# Bead: sase-p1.3 — Multi-project glossary catalog service for the TUI

[Bead Pages](../README.md) / [sase-p1](README.md) / sase-p1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.056](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.056.md) · **Assignee:** `sase-p1.3` · **Size:** medium
**Created:** 2026-08-17 17:42:38 EDT · **Closed:** 2026-08-17 19:38:55 EDT
**Plan:** [202608/glossary\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_panel.md)

## Description

catalog: add the ACE-side service that builds the ordered project ring for `p`/`P`, loads and compiles each project's glossary off the event loop behind an mtime-keyed snapshot cache, exposes outbound and inbound relation lists per entry, and invalidates cleanly after a write.

## Notes

[2026-08-17T23:38:55Z · sase-p1.3] Added src/sase/ace/tui/glossary_panel_catalog.py (GlossaryProjectRef/GlossaryProjectSnapshot, build_glossary_project_ring, load_glossary_project_snapshot with mtime-keyed LRU cache, invalidate_glossary_project, glossary_entry_relations) per Phase 3 design; factored enabled_glossary_project_records and glossary_project_record_for_workspace out of src/sase/xprompt/glossary_catalog.py for reuse; added tests/ace/tui/test_glossary_panel_catalog.py covering ring ordering/dedup, launch-project-without-glossary inclusion, malformed-glossary diagnostics (ring keep + no raise), snapshot cache mtime-gated reread, single-project invalidation, and outbound/inbound relation lookup; added --epic-symbol Justfile entries for p1.4/p1.5/p1.6 consumers. Verified with just install && just check: all lint gates green and the scoped test lane escalated to the full suite (Justfile changed) and passed.

## Dependencies

- **Depends on:** [sase-p1.1](sase-p1.1.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p1.4](sase-p1.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p1.3/README.md) | [sase-p1.3](sase-p1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7275ec1`](https://github.com/sase-org/sase/commit/7275ec15a93979fdf651e39628caee54df92c65f) | feat(glossary): add TUI catalog service for the glossary panel | [sase-p1.3](sase-p1.3.md) | 2026-08-17 20:09:46 EDT |

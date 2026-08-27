# Bead: sase-uk.9 — One ref, one destination, one glyph

[Bead Pages](../README.md) / [sase-uk](README.md) / sase-uk.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ej](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ej.md) · **Assignee:** `sase-uk.9` · **Size:** small
**Created:** 2026-08-26 17:44:41 EDT · **Closed:** 2026-08-27 08:39:53 EDT
**Plan:** [202608/link\_traversing\_pager.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_traversing_pager.md)

## Description

parity: assert with one shared test that the pager and the `sase-ug` link rail resolve the same ref to the same target, glyph, accent, and dangling vocabulary, and swap the resolver onto the live `LinkIndex` when that epic has landed it.

## Notes

[2026-08-27T12:39:20Z · sase-uk.9] PROPOSED FOLLOW-UP: Relation panel link-declaration tests fail outside this phase - just check full-suite scoped lane fails tests/ace/tui/test_artifacts_relation_collapse.py because build_relation_view skips RelationKind.LINK per bead:sase-ug.10.

[2026-08-27T12:39:53Z · sase-uk.9] Implemented pager/rail parity coverage and ACE LinkIndex-backed pager resolver. Verified focused suite: .venv/bin/python -m pytest tests/pager/test_rail_parity.py tests/pager/test_app.py tests/ace/tui/test_artifact_tab_icons.py tests/ace/tui/test_artifacts_relation_collapse.py tests/ace/tui/actions/test_view_files_pager.py reached only pre-existing relation-collapse failures; focused parity/resolver suite passed. Ran just check: lint lanes passed, scoped full-suite lane failed on out-of-scope tests/ace/tui/test_artifacts_relation_collapse.py as noted.

## Dependencies

- **Blocks:** [sase-uk.10](sase-uk.10.md) ◐ · ⧖ 2026-08-26
- **Depends on:** [sase-uk.7](sase-uk.7.md) ✓ · ⧖ 2026-08-26
- **Depends on:** [sase-uk.8](sase-uk.8.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uk.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uk.9/README.md) | [sase-uk.9](sase-uk.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5fb2189`](https://github.com/sase-org/sase/commit/5fb2189c2139663a502af8d6c5d7e3d9feaaead6) | feat(pager): align link resolution with rail index | [sase-uk.9](sase-uk.9.md) | 2026-08-27 08:41:22 EDT |

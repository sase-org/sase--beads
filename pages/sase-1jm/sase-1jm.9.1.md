# Bead: sase-1jm.9.1 — Flag residue, dead code, symvision, and lazy startup

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.1` · **Size:** medium
**Created:** 2026-10-12 14:50:50 EDT · **Closed:** 2026-10-12 15:35:29 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

flag-residue: strip every override_flags(agents_archive_view=...) and flag-era duplicate test, delete stale beta comments, vestigial parameters, and the dead custom-search revival path, resolve all six epic-caused symvision symbols plus the Justfile epic-symbol row, and stop reading the Archive grouping file in AceApp.__init__.

## Notes

[2026-10-12T18:57:39Z · sase-1jx.12.1.land] sase-1jx.12.1's landing diff privatizes five of the six symvision symbols this phase was assigned to resolve, because just symvision exits 1 while they stay public and that landing's file-change gate cannot pass otherwise. Now private, with test imports updated: _archive_name_query (_archive_arrival.py), _convert_agents_pane_query (_agents_pane_query_migration.py), _load_archive_name_candidates (_node_finder_archive.py), _sync_archive_shelf (_archive_shelf.py), _ArtifactLinkGroup (widgets/decks/record/relations.py). archive_corpus_is_warm remains the Justfile --epic-symbol 'sase-1jm(archive_corpus_is_warm)' row and is still this phase's to resolve or keep. Do not re-privatize the five. The rest of flag-residue (override_flags cleanup, dead revival path, lazy Archive grouping read) is untouched.

[2026-10-12T19:34:02Z · sase-1jm.9.1--2] PROPOSED FOLLOW-UP: just check lint (test waits) flags tests/ace/tui/modals/test_new_project_create.py:771 and tests/ace/tui/modals/test_new_project_source.py:296; tools/check_test_wait_helpers reproduces the same findings on clean HEAD 101c853939. Both files are unchanged in this phase, and searches found no existing bead tracking these exact findings; no bead was created per phase instructions.

[2026-10-12T19:35:29Z · sase-1jm.9.1--2] Flag cleanup, dead revival path, symvision entries, and lazy Archive grouping load completed. Targeted Node Finder captures and both check-only snapshot runs passed; required check reaches a clean-base-reproduced test-waits issue recorded in the phase notes. Epic-symbol scan is empty.

## Dependencies

- **Blocks:** [sase-1jm.9.2](sase-1jm.9.2.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.3](sase-1jm.9.3.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.4](sase-1jm.9.4.md) ◐ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.6](sase-1jm.9.6.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.7](sase-1jm.9.7.md) ✓ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.1.md) | [sase-1jm.9.1](sase-1jm.9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ba89d2a`](https://github.com/sase-org/sase/commit/ba89d2a6db883a677c6ea0b4e2c784150a1d4ac1) | refactor(ace): remove Archive flag residue and lazy-load grouping | [sase-1jm.9.1](sase-1jm.9.1.md) | 2026-10-12 17:27:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.1--2][1] | Need the phase scope and design file | 3 |
| read-by | [agent:sase-1jx.12.1.land][2] | Need whether the archive completion phase still owns the symbols this landing privatized | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.land/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1jm.5 — Restore, fork, and copy from the Archive

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.45.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.45.linker.w0.md) · **Assignee:** `sase-1jm.5` · **Size:** medium
**Created:** 2026-10-10 06:41:18 EDT · **Closed:** 2026-10-12 05:11:08 EDT
**Plan:** [202610/agents\_archive\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view.md)

## Description

archive-actions: add the ⏎ chooser's ARCHIVE section (Restore to inbox by default, Restore and show, Fork, Open chat, Copy). Support container and marked bulk restore with skip reasons, and keep restored rows in place. Add y to copy the @agent reference on the Agents tab, plus the % copy-palette targets ported from the pane.

## Notes

[2026-10-12T08:32:49Z · sase-1jm.5] PROPOSED FOLLOW-UP: Skipped glossary strand glossary:agent-archive per epic decision glossary_archive_term=no (Archive view, in:archive scope, Restore to inbox definitions still undocumented)

[2026-10-12T08:32:56Z · sase-1jm.5] PROPOSED FOLLOW-UP: Skipped glossary strands glossary:nav-section, glossary:nav-item, glossary:agent-data-deck, glossary:agent-relation-jump-target per epic decision glossary_strand_updates=no

[2026-10-12T08:33:01Z · sase-1jm.5] PROPOSED FOLLOW-UP: Stale symvision allowlist row --epic-symbol sase-1jm.3.1(archive_read_only_context) in Justfile _lint-symvision fails since sase-1jm.3.1 closed; needs removal plus symbol cleanup by its owner

[2026-10-12T09:11:01Z · sase-1jm.5--1] PROPOSED FOLLOW-UP: just check (run 4c911f435306053e3e4a5633d48fa797) verdict no_new_failures — 10 KNOWN pre-existing only: 4 stale symvision Justfile rows (sase-1jm.3.1 archive_read_only_context already noted; sase-1jx.7.1 journal_lock/journal_lock_path/journal_path owned elsewhere) + 6 untouched pytest failures (test_agent_display_meta_priority, test_project_handler_suggest x2, test_agent_display_workflow_async, test_kind_coverage, test_app_import_budget); none touch archive-restore files

[2026-10-12T09:11:08Z · sase-1jm.5--1] Archive restore/fork/copy done and verified: full sase tool run check (run 4c911f435306053e3e4a5633d48fa797, 55053 passed) verdict no_new_failures with only the 10 KNOWN pre-existing failures (recorded as PROPOSED FOLLOW-UP); sase bead epic-symbols sase-1jm.5 shows no entries left for this phase

## Dependencies

- **Depends on:** [sase-1jm.3](sase-1jm.3.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.8](sase-1jm.8.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.5.md) | [sase-1jm.5](sase-1jm.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ebd17bf`](https://github.com/sase-org/sase/commit/ebd17bf5bf64b1d9cb8dfa5001fc880c99dfb603) | feat(agents-archive): add restore, fork, and copy actions to the Archive | [sase-1jm.5](sase-1jm.5.md) | 2026-10-12 06:06:46 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.land][1] | Confirm every sase-1jm descendant is closed before parent close | 1 |
| read-by | [agent:sase-1jx.10.1.4][2] | Need status of beads named by stale --epic-symbol rows that just check failed on | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.10.1.4/README.md

<!-- sase:referenced-by:end -->

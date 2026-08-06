# Bead: sase-fr.8 — Document close history and reopen provenance

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.8` · **Size:** small
**Created:** 2026-08-05 21:26:22 EDT · **Closed:** 2026-08-05 23:59:24 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

docs: document the close-history record, the reopen causes, the retroactive recovery from the event log, and every surface that renders it in docs/beads.md.

## Notes

[2026-08-06T03:59:24Z · sase-fr.8] Documented close history in docs/beads.md: new Close History subsection (record schema, creation triggers, reopened_by attribution caveat, retroactive event-log recovery, and every rendering surface — CLI badges/PREVIOUSLY CLOSED section/JSON/search, ACE pane, generated pages, TaskTriage gate callouts), plus updated the open/close/+1/doctor --fix-projection CLI reference entries and the event-log Closed-intervals note to reflect archiving instead of clearing. Verified: just install, just check (fmt python+markdown, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, committed plans, and scoped tests) all pass; the two test failures seen on one earlier full run (test_artifact_file_modal_copy_anchors_pdf_markdown_source_path, test_concurrent_bead_mutations_wait_past_the_old_lock_timeout) are unrelated contention/timing flakes confirmed to pass in isolation and on a clean rerun.

## Dependencies

- **Depends on:** [sase-fr.4](sase-fr.4.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fr.5](sase-fr.5.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fr.6](sase-fr.6.md) ✓ · ⧖ 2026-08-05
- **Depends on:** [sase-fr.7](sase-fr.7.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.8/README.md) | [sase-fr.8](sase-fr.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d7ac0da`](https://github.com/sase-org/sase/commit/d7ac0dab5cdfc4c2b00f102e588d5d8506b6196f) | docs(beads): document close history and reopen provenance | [sase-fr.8](sase-fr.8.md) | 2026-08-06 00:00:09 EDT |

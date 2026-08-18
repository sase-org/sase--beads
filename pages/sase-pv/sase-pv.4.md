# Bead: sase-pv.4 — Due-ness, identity, and integrity read task-type fields

[Bead Pages](../README.md) / [sase-pv](README.md) / sase-pv.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06a](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06a.md) · **Assignee:** `sase-pv.4` · **Size:** medium
**Created:** 2026-08-18 11:26:04 EDT · **Closed:** 2026-08-18 14:08:27 EDT
**Plan:** [202608/flag\_task\_type.md](https://github.com/sase-org/sase--plans/blob/main/202608/flag_task_type.md)

## Description

reads: repoint every flag-domain read path — due-state, the key and countdown chips, bead loading, registry integrity, the doctor, and the lint — from `issue.flag` to the typed task bead's field values.

## Notes

[2026-08-18T17:58:51Z · sase-pv.4] PROPOSED FOLLOW-UP: Pre-existing just check failures I did not cause — mypy src/sase/glossary/render.py:74 Console color_system type, and symvision unused publics project_accent and project_accent_map in src/sase/ace/tui/project_styles.py.

[2026-08-18T18:08:27Z · sase-pv.4] Repointed flag-domain reads through flag_fields(): due-state takes the two thresholds (not FlagRecord); chips, bead snapshots, doctor integrity, sase flag list/show, and --remove-by follow the accessor. load_flag_bead_snapshots lists TASK(flag) plus legacy FLAG so the coexistence window stays readable; wrong_type now says 'not a flag task bead'; kind_mismatch catches registry/bead kind and default-vs-kind drift. --remove-by writes task_type_fields on flag task beads (Rust update gained task_type_fields) and still writes FlagRecord on legacy FLAG beads. just _lint-flags green; cargo test update_replaces_task_type_fields_and_replays_from_events passed; just test-scoped escalated (core-identity-changed) to 33451 passed, 13 skipped. No leftover --epic-symbol entries. just check still fails on pre-existing mypy (glossary/render.py) and symvision (project_accent*) — recorded as PROPOSED FOLLOW-UP. sase-core events.rs/mutation.rs are updated in the linked checkout and still uncommitted.

[2026-08-18T18:09:59Z · sase-pv.4] Repointed flag-domain reads through flag_fields(): due-state takes the two thresholds (not FlagRecord); chips, bead snapshots, doctor integrity, sase flag list/show, and --remove-by follow the accessor. load_flag_bead_snapshots lists TASK(flag) plus legacy FLAG so the coexistence window stays readable; wrong_type now says 'not a flag task bead'; kind_mismatch catches registry/bead kind and default-vs-kind drift. --remove-by writes task_type_fields on flag task beads (Rust update gained task_type_fields) and still writes FlagRecord on legacy FLAG beads. just _lint-flags green; cargo test update_replaces_task_type_fields_and_replays_from_events passed; just test-scoped escalated (core-identity-changed) to 33451 passed, 13 skipped. No leftover --epic-symbol entries. just check still fails on pre-existing mypy (glossary/render.py) and symvision (project_accent*) — recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-pv.2](sase-pv.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.5](sase-pv.5.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pv.6](sase-pv.6.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pv.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pv.4/README.md) | [sase-pv.4](sase-pv.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c5a0dcf`](https://github.com/sase-org/sase/commit/c5a0dcf4a4f3b56f548af1e02377c1c0daa9188f) | feat(flags): read flag identity and due-ness from task fields | [sase-pv.4](sase-pv.4.md) | 2026-08-18 14:13:11 EDT |
| sase-core | [`sase-core@c121e0e`](https://github.com/sase-org/sase-core/commit/c121e0ed6bfbd1e11fa4ca27ab166f7dcf63db8d) | feat(bead): persist task\_type\_fields on bead update | [sase-pv.4](sase-pv.4.md) | 2026-08-18 14:16:26 EDT |

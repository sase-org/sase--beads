# Bead: sase-1jx.13.1 — Keep explicit create settings and fix candidate classification

[Bead Pages](../README.md) / [sase-1jx.13](sase-1jx.13.md) / sase-1jx.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.land.md) · **Assignee:** `sase-1jx.13.1` · **Size:** medium
**Created:** 2026-10-12 14:55:55 EDT · **Closed:** 2026-10-12 15:36:14 EDT
**Plan:** [202610/new\_project\_wizard\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/new_project_wizard_landing_repairs.md)

## Description

core-repairs: in sase-core project_onboarding, keep explicitly-off bool fields in effective_options, stop strict mode from flagging harmless off values of excluded fields, stop a numbered sibling from hiding its primary checkout, stop inventory seeding from creating ref-less rows, and move sase's core pin.

## Notes

[2026-10-12T19:36:14Z · sase-1jx.13.1] core-repairs done in linked sase-core (crates/sase_core/src/project_onboarding/): explicit-false bools now kept in effective_options; strict mode ignores off/empty values on excluded fields but keeps real conflicts (template+gitignore=Python still errors); primary+numbered sibling merges to LOCAL with the primary path in both input orders; inventory no longer seeds rows so inventory-only identities emit nothing ref-less. Verified: sase-core 'sase tool run check' exit 0 (incl. 4 new/updated table tests); sase 'just test tests/core/test_project_onboarding_facade.py tests/project_onboarding/' 150 passed against the rebuilt extension; live-binding probe confirmed all four behaviors. No wire-shape changes, no sase-file changes, epic-symbols clean. Pin NOT moved: the core fix is uncommitted (agents never commit), so no new sase-core commit exists for sase-core-revision.txt to move past; land agent must commit in sase-core then ratchet.

## Dependencies

- **Blocks:** [sase-1jx.13.3](sase-1jx.13.3.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.13.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.13.1/README.md) | [sase-1jx.13.1](sase-1jx.13.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@98c3682`](https://github.com/sase-org/sase-core/commit/98c3682f293892a4e9c9a31fa25dd0a05517d367) | fix(project-onboarding): keep explicit off bools, strict excluded-field conflicts, primary-sibling LOCAL merge, annotation-only inventory | [sase-1jx.13.1](sase-1jx.13.1.md) | 2026-10-12 15:37:56 EDT |

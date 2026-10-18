# Bead: sase-1mk.9.4 — Fix the New Project create-form readiness regression on owner switch

[Bead Pages](../README.md) / [sase-1mk.9](sase-1mk.9.md) / sase-1mk.9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.land.md) · **Assignee:** `sase-1mk.9.4` · **Size:** medium
**Created:** 2026-10-18 16:48:00 EDT · **Closed:** 2026-10-18 17:35:41 EDT
**Plan:** [202610/ship\_v0\_18\_0\_post\_repair\_reds.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_post_repair_reds.md)

## Description

new-project-owner: fix the sase-1mk.6 RepoCreationFormWidget readiness regression that strands the create form after an owner switch in every Full CI leg.

## Notes

[2026-10-18T21:17:53Z · sase-1mk.9.4] Phase evidence: fixed RepoCreationFormWidget control-readiness so owner-switch remounts cannot query missing #repo-creation-form-errors. _controls_ready now resets on unmount, re-arms on every mount, and _ready_to_touch_controls() clears the flag when composed controls are absent. Create-form paint retries once after refresh if it still raises, so a paint failure cannot strand _create_form_status at loading. Programmatic owner-switch restores are ignored as project-name edits (_syncing + ignore-map). Addresses the sase-1mk.6 regression (Master Gate 39159243248 test (8) and Full CI 39155173153 all three test legs). sase-1mi (test_name_collision_blocks_review_but_occupied_checkout_surfaces) and sase-1m9 (test_review_back_restores_draft_and_y_stores_model_submission) still pass. Stress: 20/20 iterations under SASE_PYTEST_WORKERS=8 of create_flow + create_races + configure_review + repo_creation_form + create + create_defaults (40 tests/iter, 800 passed). Full tests/ace/tui/modals/test_new_project_*.py: 192 passed. No --epic-symbol leftovers.

[2026-10-18T21:35:41Z · sase-1mk.9.4--mon] Closed by explicit `sase stitch create -B close` after create_commit landed 7f3c8d0965 ("fix(ace): keep New Project form controls ready after owner switch"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1mk.9.4` if more work remains.

## Dependencies

- **Blocks:** [sase-1mk.9.6](sase-1mk.9.6.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.9.4.md) | [sase-1mk.9.4](sase-1mk.9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7f3c8d0`](https://github.com/sase-org/sase/commit/7f3c8d0965b2c7df116ba254ae07fd320f88eab1) | fix(ace): keep New Project form controls ready after owner switch | [sase-1mk.9.4](sase-1mk.9.4.md) | 2026-10-18 17:34:27 EDT |

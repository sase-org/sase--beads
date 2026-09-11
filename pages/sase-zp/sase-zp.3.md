# Bead: sase-zp.3 — Add capacity to epic approval controls

[Bead Pages](../README.md) / [sase-zp](README.md) / sase-zp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jl.md) · **Assignee:** `sase-zp.3` · **Size:** medium
**Created:** 2026-09-11 13:40:29 EDT · **Closed:** 2026-09-11 18:34:28 EDT
**Plan:** [202609/bead\_work\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_capacity.md)

## Description

epic_gate_capacity: expose capacity in gate schemas and the custom approval modal, retain it through response translation, and pass it into the epic launcher.

## Notes

[2026-09-11T22:33:16Z · sase-zp.3] PROPOSED FOLLOW-UP: test_fleet_catalog_refresh_requests_legal_pages_and_logical_keys fails in isolation — expected a second catalog page request, got none (tests/ace/tui/test_agents_fleet_refresh_laziness.py). Unrelated to epic gate capacity; reproduced after the capacity suite.

[2026-09-11T22:33:50Z · sase-zp.3] PROPOSED FOLLOW-UP: test_d_resolves_to_description_on_axe_and_diff_on_prs raises textual ScreenStackError: No screens on stack in check_action/_prompt_input_owns_keys (tests/ace/tui/test_axe_navigation.py). Unrelated to epic gate capacity; reproduced in isolation.

[2026-09-11T22:34:28Z · sase-zp.3] Exposed optional integer capacity on epic approve input/result schemas, retained it through command/translation/adapter/legacy paths, and added an epic-only Custom Approval Capacity control (c). Verified: pytest tests/test_plan_gate_capacity.py plus wait/schema/modal/TUI suites (122 then 57 after help-test fix); default/zero/omission, skip/reject no launch, invalid input leaves the gate unconsumed, exactly one launch with --capacity; git diff --check clean; just check fmt/ruff/mypy passed then stopped on pre-existing feature-flag lint (sase-z9 / completion_managed_install_recipe) and later pre-existing symvision (sase-zk) and toobig (continuation_capture.py); scoped tests 5898 passed, help assertion updated for -c/--capacity and -C/--cl-name; epic-symbols clear.

## Dependencies

- **Depends on:** [sase-zp.2](sase-zp.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zp.4](sase-zp.4.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zp.3/README.md) | [sase-zp.3](sase-zp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`41806ee`](https://github.com/sase-org/sase/commit/41806ee9885fc09d09b64d9df4614664def9ba8c) | feat(plan-gate): add capacity to epic approval controls | [sase-zp.3](sase-zp.3.md) | 2026-09-11 18:36:14 EDT |

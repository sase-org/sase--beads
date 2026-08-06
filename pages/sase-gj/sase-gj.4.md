# Bead: sase-gj.4 — Attribute and narrow the core-identity-changed escalation

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.4` · **Size:** small
**Created:** 2026-08-06 16:02:43 EDT · **Closed:** 2026-08-06 16:45:05 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

identity: record which fingerprint input changed, and stop forcing the whole suite for environment churn that is byte-identical or already covered by another rule.

## Notes

[2026-08-06T20:44:40Z · sase-gj.4] PROPOSED FOLLOW-UP: tests/test_test_selection.py is now 706 lines, past the toobig info threshold (700) though below the warning threshold (850) — the identity phase added tests here (per the plan) and the module is close to needing the split the plan phase docs anticipate.

[2026-08-06T20:45:05Z · sase-gj.4] Replaced the single opaque environment digest with a per-input fingerprint map (tools/validate_test_environment._fingerprint_inputs, tests/_test_selection_manifest.environment_fingerprint/environment_changed_inputs); core-identity-changed now fires only when a bucket in ENVIRONMENT_ESCALATING_INPUTS (pyproject, uv-lock, venv-config, core-cargo, extension, python) changed, with every changed bucket recorded on the manifest (schema bumped to 5) and surfaced via 'tools/select_tests --explain'. Fixed _STATED_EXTENSION_PATTERNS (renamed _EXTENSION_PATTERNS) to search the nested site-packages/sase_core_rs/ dir so it actually matches sase_core_rs.abi3.so, and switched the extension input from stat() to content hash. Documented the narrowed rule and the extension-glob fix in docs/development.md. Verified: uv run pytest tests/test_validate_test_environment_tool.py tests/test_test_selection.py tests/test_select_tests_tool.py (86 passed) and pytest tests/ -k selection (506 passed, 1 skipped); just lint clean (ruff, mypy, symvision, toobig — 0 issues); just check green after just fmt fixed two lines ruff-format flagged in the new tests (scoped stage correctly escalated to full suite via selection-tooling since the diff touches tests/_test_selection*.py itself).

## Dependencies

- **Blocks:** [sase-gj.7](sase-gj.7.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.4/README.md) | [sase-gj.4](sase-gj.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f88b740`](https://github.com/sase-org/sase/commit/f88b7403cd0dcc2d5522d909582a7cdbddbb1304) | fix(test-selection): attribute and narrow the core-identity-changed escalation | [sase-gj.4](sase-gj.4.md) | 2026-08-06 16:47:36 EDT |

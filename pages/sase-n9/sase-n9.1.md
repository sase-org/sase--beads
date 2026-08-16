# Bead: sase-n9.1 — Shared family plan-preview value and TUI resolution cache

[Bead Pages](../README.md) / [sase-n9](README.md) / sase-n9.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03u.md) · **Assignee:** `sase-n9.1` · **Size:** medium
**Created:** 2026-08-16 12:00:21 EDT · **Closed:** 2026-08-16 12:57:13 EDT
**Plan:** [202608/agent\_family\_completion\_previews.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_family_completion_previews.md)

## Description

preview: add the surface-neutral AgentFamilyPlanPreview value plus its shared text formatters, and the TTL-cached TUI resolver that warms previews from agent rows off the render path.

## Notes

[2026-08-16T16:55:45Z · sase-n9.1--3] PROPOSED FOLLOW-UP: tests/test_config.py::test_machine_overlays_require_matching_selector_and_keep_ordinary_overlays failed once in a full just-check suite run but passed in isolation and passed when run with its whole file (33/33) — looks like a flaky/order-dependent test under the full parallel suite, worth investigating test isolation for sase.config.core CONFIG_DIR caching under xdist.

[2026-08-16T16:57:13Z · sase-n9.1--3] Implemented src/sase/agent_family_plan_preview.py and src/sase/ace/tui/models/agent_family_preview_cache.py with tests. just check passed clean (fmt, lint, mypy, symvision, toobig, and full test suite via scoped-to-full escalation: 31160 passed, 10 skipped). One unrelated flaky test (test_config.py::test_machine_overlays_require_matching_selector_and_keep_ordinary_overlays) failed once under the full parallel suite but passed standalone and with its whole file; recorded as a PROPOSED FOLLOW-UP note, not a regression from this bead's changes.

[2026-08-16T17:00:55Z · sase-n9.1--3] just check passed: fmt, ruff, mypy, symvision, and full test suite (31160 passed, 10 skipped) all green. Verified agent_family_plan_preview.py and agent_family_preview_cache.py plus their tests. One unrelated flaky test_config.py failure seen in an earlier full-suite run was recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-n9.2](sase-n9.2.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n9.3](sase-n9.3.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-n9.4](sase-n9.4.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n9.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n9.1.md) | [sase-n9.1](sase-n9.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ddef1f0`](https://github.com/sase-org/sase/commit/ddef1f0d42a711729b6e322a6575e47fe3046a3a) | feat(ace): share agent-family plan/bead preview across TUI and editor | [sase-n9.1](sase-n9.1.md) | 2026-08-16 13:08:14 EDT |

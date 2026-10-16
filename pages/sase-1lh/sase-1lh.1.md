# Bead: sase-1lh.1 — Fix every Master Gate red at master HEAD

[Bead Pages](../README.md) / [sase-1lh](README.md) / sase-1lh.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10q](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10q.md) · **Assignee:** `sase-1lh.1` · **Size:** medium
**Created:** 2026-10-16 13:00:19 EDT
**Plan:** [202610/v0\_18\_0\_green\_ci\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_green_ci_release.md)

## Description

gate-fix: clear the mypy, docs-test, and docs-lint reds the docs restructuring left on master, then prove every lint-job step locally.

## Notes

[2026-10-16T17:28:24Z · sase-1lh.1] PROPOSED FOLLOW-UP: Track the CI-only JSONDecodeError for tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent under existing flake bead sase-1k2. It failed in Master Gate runs 38935192508 and 38935262082; the targeted test passed locally on the clean current tree, so gate-fix made no provider-drain changes.

[2026-10-16T17:31:16Z · sase-1lh.1] PROPOSED FOLLOW-UP: On local Python 3.14, `sase tool run check` fails at docs-gen-check with generated CLI usage diffs. It reproduced identically on clean base (ToolRun 940cef208af24b0a50dcea2249b13636) and with this phase diff (ToolRun 787c96274925aa951145cad19efe811f); current Master Gate on Python 3.12 passes. Existing follow-up sase-1lh.4 note 1 records the same docs-epic-owned drift; no CLI generator change belongs in gate-fix.

## Dependencies

- **Blocks:** [sase-1lh.6](sase-1lh.6.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.1/README.md) | [sase-1lh.1](sase-1lh.1.md) | 0 |

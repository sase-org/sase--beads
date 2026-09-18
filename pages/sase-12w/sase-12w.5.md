# Bead: sase-12w.5 — Detach becomes the default answer mode

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.5` · **Size:** small
**Created:** 2026-09-18 08:50:42 EDT · **Closed:** 2026-09-18 13:31:39 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

default: flip `sase sudo answer --run` to detach by default with --no-detach keeping the synchronous path, matching the shell-backed `sase gate answer` convention; update help text and tests.

## Notes

[2026-09-18T17:31:13Z · sase-12w.5] PROPOSED FOLLOW-UP: SDD sidecar clone/materialization tests fail in this workspace — focused rerun of tests/sdd_store/test_sidecar_bead_adoption.py, tests/sdd_store/test_sidecar_init_creation.py, tests/sdd_store/test_sidecar_init_reconciliation.py, and tests/test_linked_repo_workspaces.py::test_sidecar_materialization_uses_remote_not_divergent_primary reproduces staged clones without resolvable HEAD plus one staging-path expectation drift.

[2026-09-18T17:31:39Z · sase-12w.5] Implemented sudo answer detach-by-default with --no-detach foreground override; updated help, docs, tests, and completion snapshot. Verified no epic symbols remain. Focused .venv pytest for sudo parser/detach/gate/acceptance plus completion snapshot passed (60 passed). just fmt passed. just check lint stages passed and completion drift was fixed; its escalated full-suite test lane still fails on pre-existing SDD sidecar materialization tests reproduced separately.

## Dependencies

- **Depends on:** [sase-12w.3](sase-12w.3.md) ✓ · ⧖ 2026-09-18
- **Depends on:** [sase-12w.4](sase-12w.4.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.5/README.md) | [sase-12w.5](sase-12w.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a26bfc8`](https://github.com/sase-org/sase/commit/a26bfc839d51664baaa629522483234d60aa3d33) | feat(sudo): default approvals to detached execution | [sase-12w.5](sase-12w.5.md) | 2026-09-18 13:33:19 EDT |

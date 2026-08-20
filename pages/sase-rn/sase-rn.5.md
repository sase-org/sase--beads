# Bead: sase-rn.5 — Isolated plugin and configuration finalizer execution

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.5` · **Size:** medium
**Created:** 2026-08-20 16:35:05 EDT · **Closed:** 2026-08-20 18:32:48 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

extension-runtime: implement the `sase_finalizers` subprocess protocol with sanitized environments and bounded JSON I/O, add constrained `builtin@command`, surface activation and provenance through `sase final list`, `show`, and `doctor`, and prove with a non-mutating reference plugin that installation alone never activates behavior.

## Notes

[2026-08-20T22:31:52Z · sase-rn.5] PROPOSED FOLLOW-UP: fix stale closed flag bead admin_center_config_hub — just check fails in tools/check_feature_flags because closed flag bead sase-rk still has a surviving admin_center_config_hub definition.

[2026-08-20T22:32:48Z · sase-rn.5] Implemented finalizer provider discovery, builtin@command/plugin execution runtime, finalizer result artifacts, and sase final list/show/doctor. Verified focused finalizer tests (12 passed), editable CLI list/show smoke, git diff --check, and just check through fmt/ruff/mypy; just check is blocked afterward by pre-existing feature-flag lint on closed bead sase-rk/admin_center_config_hub, recorded as PROPOSED FOLLOW-UP.

[2026-08-20T22:34:45Z · sase-rn.5] Additional verification after completion spec refresh: tests/completion/test_snapshot.py plus focused finalizer tests passed (16 passed); just check rerun again passed fmt/markdown/keep-sorted/ruff/mypy and remains blocked only by pre-existing feature-flag lint on closed bead sase-rk/admin_center_config_hub.

[2026-08-20T22:36:27Z · sase-rn.5] Verified focused finalizer runtime and completion tests, final list/show CLI smoke, clean epic-symbols; just check only blocked by unrelated existing admin_center_config_hub closed-flag lint.

## Dependencies

- **Depends on:** [sase-rn.3](sase-rn.3.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.6](sase-rn.6.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.5/README.md) | [sase-rn.5](sase-rn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`78550c9`](https://github.com/sase-org/sase/commit/78550c993bedfd12be3a4338c7f5004460120605) | feat: add pluggable finalizer execution runtime | [sase-rn.5](sase-rn.5.md) | 2026-08-20 18:38:01 EDT |

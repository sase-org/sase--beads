# Bead: sase-4h.5 — Phase 5: Documentation And Final Polish

[Bead Pages](../README.md) / [sase-4h](README.md) / sase-4h.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4h.5`
**Created:** 2026-06-08 19:29:58 UTC · **Closed:** 2026-06-08 20:53:50 UTC
**Plan:** [202606/version\_command.md](https://github.com/sase-org/sase--plans/blob/main/202606/version_command.md)

## Notes

COMMIT: 2565dd708

[2026-07-27T21:33:14Z · sase-a1.land] [2026-06-08T20:49:28Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Completed Phase 5 documentation and final polish.

Changes:
- Documented `sase version` in `docs/cli.md`, `docs/configuration.md`, and `docs/rust_backend.md`.
- Clarified that `sase version` reports the local runtime, not latest available releases.
- Documented PEP 440 development versions, stale editable metadata handling, JSON schema/version flags, and the relationship to `sase core health`.
- Fixed `tools/validate_dependency_group` to resolve the repo `pyproject.toml` script-relative after `just check` exposed cwd-sensitive test isolation.

Verification:
- `just install`
- `just docs-check`
- `.venv/bin/sase version` and `.venv/bin/sase version --json`: schema_version=1, packages include `sase` and `sase-core-rs`.
- `PYTHONPATH=$PWD/src sase version` and `PYTHONPATH=$PWD/src sase version --json` in the uv-tool runtime: schema_version=1, packages include `sase`, `sase-core-rs`, `sase-github`, and `sase-telegram`. Plain global `sase` is still the older editable install until its source is updated.
- `.venv/bin/python -m pytest tests/test_validate_dependency_group_tool.py`
- `just check`

## Dependencies

- **Depends on:** [sase-4h.4](sase-4h.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4h.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4h.5/README.md) | [sase-4h.5](sase-4h.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9cde44b`](https://github.com/sase-org/sase/commit/9cde44be6ae5f978aa729568af016cee135f1474) | chore: document version runtime inventory (sase-4h.5) | [sase-4h.5](sase-4h.5.md) | 2026-06-08 20:54:17 |

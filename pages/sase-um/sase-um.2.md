# Bead: sase-um.2 — ci\_watch gating allowlist, heavy-lane freshness, and merge strategy

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.2` · **Size:** large
**Created:** 2026-08-26 19:12:24 EDT · **Closed:** 2026-08-26 19:50:26 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

chop: teach ci_watch a gating_workflows allowlist evaluated against HEAD-scoped runs, add a heavy-lane green-and-fresh release condition, switch the release merge to the repository's allowed merge-commit strategy, and cut a bugyi-chops release.

## Notes

[2026-08-26T23:50:26Z · sase-um.2] Verified in bugyi-chops (bbugyi200/bugyi-chops): full tests/test_ci_watch.py suite plus ruff format/check, mypy, python -m build, and twine check all pass (104 tests, 93.27% coverage, gate 90%). Bumped pyproject.toml/uv.lock to 0.8.0 for the tag-driven publish workflow. No sase-um.2 epic symbols remained to resolve.

## Dependencies

- **Blocks:** [sase-um.7](sase-um.7.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.2.md) | [sase-um.2](sase-um.2.md) | 0 |

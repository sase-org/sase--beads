# Bead: sase-zp.2 — Carry capacity through epic work and launch handoffs

[Bead Pages](../README.md) / [sase-zp](README.md) / sase-zp.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0jl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0jl.md) · **Assignee:** `sase-zp.2` · **Size:** medium
**Created:** 2026-09-11 13:40:29 EDT · **Closed:** 2026-09-11 17:23:14 EDT
**Plan:** [202609/bead\_work\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_capacity.md)

## Description

bead_capacity: add -c/--capacity, move --cl-name to -C, and preserve capacity across all epic rendering, resume, and launch paths.

## Notes

[2026-09-11T21:22:12Z · sase-zp.2] PROPOSED FOLLOW-UP: Feature flag lint is already red for live flag bead sase-z9 - check_feature_flags reports missing registry definition for completion_managed_install_recipe.

[2026-09-11T21:23:14Z · sase-zp.2] Implemented capacity propagation for bead work and epic launch handoffs. Verified targeted capacity suite: .venv/bin/python -m pytest ... (130 passed); git diff --check clean; just check passed fmt/ruff/mypy then stopped on unrelated feature-flag lint for live flag bead sase-z9 missing completion_managed_install_recipe; epic-symbols clear.

## Dependencies

- **Depends on:** [sase-zp.1](sase-zp.1.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zp.3](sase-zp.3.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zp.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zp.2/README.md) | [sase-zp.2](sase-zp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`39cc0c4`](https://github.com/sase-org/sase/commit/39cc0c4b8bae36e6edaed6201051bc85eb460802) | feat(bead): propagate work queue capacity | [sase-zp.2](sase-zp.2.md) | 2026-09-11 17:26:30 EDT |

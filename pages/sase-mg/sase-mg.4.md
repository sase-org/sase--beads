# Bead: sase-mg.4 — Synchronize the sase\_var skill and verify the complete workflow

[Bead Pages](../README.md) / [sase-mg](README.md) / sase-mg.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02u.md) · **Assignee:** `sase-mg.4` · **Size:** small
**Created:** 2026-08-15 15:37:18 EDT · **Closed:** 2026-08-15 18:25:26 EDT
**Plan:** [202608/powerful\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202608/powerful_variables.md)

## Description

skill-and-integration: teach agents only the new show replacement, exercise end-to-end behavior, and run repository-wide verification without exposing historical discovery in the skill yet.

## Notes

[2026-08-15T22:24:13Z · sase-mg.4] PROPOSED FOLLOW-UP: fix local-core dev install downgrade — `just install` builds sase_core_rs 0.27.8 from the linked checkout, but the final uv dependency sync reinstalls published 0.27.7 from the lockfile, hiding the new output-variable bindings unless `just rust-install` is run afterward or uv sync is avoided.

[2026-08-15T22:25:26Z · sase-mg.4] Updated sase_var skill/docs to use 'sase var show' and 'sase var show --format json'; added end-to-end var CLI workflow coverage. Verified: sase skill init --diff; .venv/bin/pytest tests/main/test_var_integration.py tests/main/test_init_skills_sources.py -q; .venv/bin/pytest tests/main/test_var_*.py -q; just check.

[2026-08-15T22:27:01Z · sase-mg.4] Verified skill source/docs updates and variable CLI workflow with focused pytest lanes, sase skill init --diff, full var CLI tests, and just check.

## Dependencies

- **Depends on:** [sase-mg.3](sase-mg.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mg.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.4/README.md) | [sase-mg.4](sase-mg.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4d81923`](https://github.com/sase-org/sase/commit/4d81923528a7d38c1ba9632fbc403c94b12ebd09) | feat: document current variable inspection workflow | [sase-mg.4](sase-mg.4.md) | 2026-08-15 18:28:24 EDT |

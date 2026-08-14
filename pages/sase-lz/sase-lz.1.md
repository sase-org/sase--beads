# Bead: sase-lz.1 — Reject selector expressions in the temporary-override path

[Bead Pages](../README.md) / [sase-lz](README.md) / sase-lz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.014](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.014.md) · **Assignee:** `sase-lz.1` · **Size:** small
**Created:** 2026-08-14 10:49:23 EDT · **Closed:** 2026-08-14 11:00:41 EDT
**Plan:** [202608/models\_panel\_pool\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/models_panel_pool_authoring.md)

## Description

override-selector-reject: detect selector syntax with parse_model_alias_selector in the panel's Custom Override Model flow and refuse it with a message pointing at the persistent Edit key, instead of letting a pool string split on its first slash and persist a bogus single-target override.

## Notes

[2026-08-14T15:00:41Z · sase-lz.1] Added parse_model_alias_selector-based selector detection to _on_custom_picked in models_panel_override.py; selector expressions (round-robin |, fallback ||, or mixed) are now rejected with a warning pointing at the persistent Edit key instead of being silently split into a bogus single-target override. Added 4 new tests covering round-robin rejection, fallback rejection, mixed-syntax rejection, and a regression check that alias-references to pool-owning aliases still snapshot correctly. Verified: targeted suite (.venv/bin/python -m pytest tests/test_models_panel_override_flows.py) 17 passed; just check (fmt, ruff, mypy, pyscripts, symvision, sase validate, scoped tests) exit 0.

## Dependencies

- **Blocks:** [sase-lz.2](sase-lz.2.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lz.1/README.md) | [sase-lz.1](sase-lz.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`adea6b1`](https://github.com/sase-org/sase/commit/adea6b1dfcc250fe7cfc8f4e756d105338f4e2da) | fix(ace): reject selector expressions in the temporary-override picker | [sase-lz.1](sase-lz.1.md) | 2026-08-14 11:01:28 EDT |

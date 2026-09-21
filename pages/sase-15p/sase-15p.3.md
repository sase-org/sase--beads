# Bead: sase-15p.3 — Header naming polish, default config, and snapshots

[Bead Pages](../README.md) / [sase-15p](README.md) / sase-15p.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0os](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0os.md) · **Assignee:** `sase-15p.3` · **Size:** small
**Created:** 2026-09-21 15:31:55 EDT · **Closed:** 2026-09-21 17:53:58 EDT
**Plan:** [202609/agy\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/agy_usage_windows.md)

## Description

header-default: render model_family scopes as the bare family in compact header names only, add commented agy indicator examples to default_config.yml, pin the shipped-default agy header outcome in tests, and add agy visual snapshot coverage.

## Notes

[2026-09-21T21:52:54Z · sase-15p.3] PROPOSED FOLLOW-UP: tests/llm_provider/test_usage_config.py still asserts the pre-c00964773 shipped Fable pin (KeyError claude); update it to the generic-threshold default

[2026-09-21T21:53:24Z · sase-15p.3] PROPOSED FOLLOW-UP: test_agy_usage_probe_auth_prompt_is_logged_out_fast returns error instead of unauthenticated (phase-2 collector scope, marker match looks right)

[2026-09-21T21:53:58Z · sase-15p.3] header-default done: compact model_family names (5h/gemini, 3p), commented agy defaults in default_config.yml (no active entry, schema untouched), 6 shipped-default tests + 3 inspected PNG goldens (60/80/140) all passing; ruff/mypy/symvision clean. just check: 44591 passed, 22 failed, all 22 proven pre-existing/out-of-phase-scope (4 stale usage_config from c00964773, 1 phase-2 probe timing filed as follow-ups). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-15p.2](sase-15p.2.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15p.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15p.3/README.md) | [sase-15p.3](sase-15p.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`80c0f54`](https://github.com/sase-org/sase/commit/80c0f549e4dba7467756f2827c05940b82f9b3e5) | feat(agy): header naming polish, default config, and snapshots | [sase-15p.3](sase-15p.3.md) | 2026-09-21 17:56:08 EDT |

# Bead: sase-16g.6 — The captured service environment is context-safe

[Bead Pages](../README.md) / [sase-16g](README.md) / sase-16g.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pe.md) · **Assignee:** `sase-16g.6` · **Size:** medium
**Created:** 2026-09-22 12:59:13 EDT · **Closed:** 2026-09-22 13:19:42 EDT
**Plan:** [202609/services\_p0\_supervision.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_p0_supervision.md)

## Description

env: stop capturing SASE_FEATURE_FLAGS into the host environment, settle the currency check by ignoring volatile keys and normalizing PATH, and refuse an agent-context `sase service init --yes` unless it is explicitly allowed.

## Notes

[2026-09-22T17:19:42Z · sase-16g.6] env phase done: dropped SASE_FEATURE_FLAGS from capture (CAPTURED_BASE_ENV_NAMES), settled environment_files_match (ignores SSH handles, normalizes PATH), apply_service_init refuses agent/ephemeral shells with exit 2 unless -a/--allow-agent-env; docs updated. Verified: 60 focused tests pass (environment, platform_init, readiness, parser_service_scheduler) + 24 platform linux/darwin/executable tests pass after just install; sase tool run check lint gates ruff/mypy/fmt pass but pyscripts gate fails pre-existing (visual tool placement, untouched by this diff).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16g.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.6/README.md) | [sase-16g.6](sase-16g.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2ce4998`](https://github.com/sase-org/sase/commit/2ce4998e9a164ccc6230df199e4e6b8ee4e7d809) | feat(service): make captured service environment context-safe | [sase-16g.6](sase-16g.6.md) | 2026-09-22 13:21:52 EDT |

# Bead: sase-n.4 — Phase 4 — Extract external provider to plugin repo

[Bead Pages](../README.md) / [sase-n](README.md) / sase-n.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 18:03:09 UTC · **Closed:** 2026-04-24 18:42:32 UTC
**Plan:** /home/bryan/projects/github/sase-org/sase/plans/202604/llm\_provider\_plugins.md

## Description

Physically move the external provider to its plugin repo. Delete src/sase/llm_provider/external_provider.py, tests/test_llm_provider_external_provider.py, the external provider entry-point line in pyproject.toml, and any remaining documentation. In ../retired Mercurial plugin: create src/retired_mercurial_plugin/llm_external_provider/provider.py with all Phase 3 @hookimpl metadata methods, move the test file, declare the sase_llm entry point. Verify sase init-skills works both with and without retired Mercurial plugin installed.

## Notes

COMMIT: 6c8bf23b

## Dependencies

- **Depends on:** [sase-n.3](sase-n.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4dce69c`](https://github.com/sase-org/sase/commit/4dce69c1b127ec477ed4e18714e2d2f639186327) | ref: extract jetski LLM provider to sase-google (sase-n.4) | [sase-n.4](sase-n.4.md) | 2026-04-24 18:42:35 |

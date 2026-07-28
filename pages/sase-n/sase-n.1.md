# Bead: sase-n.1 — Phase 1 — Foundation: hookspec + plugin manager, zero behavior change

[Bead Pages](../README.md) / [sase-n](README.md) / sase-n.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 18:02:53 UTC · **Closed:** 2026-04-24 18:11:50 UTC
**Plan:** /home/bryan/projects/github/sase-org/sase/plans/202604/llm\_provider\_plugins.md

## Description

Introduce the pluggy plumbing in parallel with the existing registry. Create src/sase/llm_provider/_hookspec.py with LLMHookSpec (llm_invoke, llm_resolve_model_name, llm_provider_name), src/sase/llm_provider/_plugin_manager.py with LLMPluginManager(LLMProvider), and unit tests. Do not touch registry.py, existing providers, or pyproject.toml entry points. Existing _REGISTRY must still power get_provider() unchanged.

## Notes

COMMIT: 2daa5f7b

## Dependencies

- **Blocks:** [sase-n.2](sase-n.2.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`863a0d9`](https://github.com/sase-org/sase/commit/863a0d99c96798be4520575bae40e53f9a6ddf74) | feat: add pluggy hookspec and plugin manager for LLM providers (sase-n.1) | [sase-n.1](sase-n.1.md) | 2026-04-24 18:11:53 |

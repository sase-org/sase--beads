# Bead: sase-n.2 — Phase 2 — Convert the four in-tree providers to pluggy + entry points

[Bead Pages](../README.md) / [sase-n](README.md) / sase-n.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 18:02:58 UTC · **Closed:** 2026-04-24 18:20:14 UTC
**Plan:** /home/bryan/projects/github/sase-org/sase/plans/202604/llm\_provider\_plugins.md

## Description

Replace _REGISTRY and _register_builtin_providers with entry-point-based discovery. Add @hookimpl methods to claude, codex, gemini, and external provider adapters. Rewrite registry.py to walk importlib.metadata.entry_points(group='sase_llm'). Update pyproject.toml with [project.entry-points.sase_llm] declarations. An external provider stays in sase for this phase.

## Notes

COMMIT: 4a52f99b

## Dependencies

- **Depends on:** [sase-n.1](sase-n.1.md) ✓
- **Blocks:** [sase-n.3](sase-n.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`30d6330`](https://github.com/sase-org/sase/commit/30d6330f596411678d5d59003bd579cfb9a2b8ff) | feat: migrate built-in LLM providers to pluggy entry points (sase-n.2) | [sase-n.2](sase-n.2.md) | 2026-04-24 18:20:18 |

# Bead: sase-n.3 — Phase 3 — Generalize provider metadata via hooks

[Bead Pages](../README.md) / [sase-n](README.md) / sase-n.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-24 18:03:04 UTC · **Closed:** 2026-04-24 18:31:43 UTC
**Plan:** /home/bryan/projects/github/sase-org/sase/plans/202604/llm\_provider\_plugins.md

## Description

Remove every remaining hardcoded provider list / table from sase core. Add hooks: llm_known_model_names, llm_skill_template_context, llm_skill_deploy_subpath, llm_cli_status_color, llm_autodetect_priority, llm_autodetect_cli_name, llm_default_retry_config. Refactor registry.py, init_skills_handler.py, cli_status.py, retry_config.py to consult plugins via a shared memoized PM factory (_build_llm_pm).

## Notes

COMMIT: e892a718

## Dependencies

- **Depends on:** [sase-n.2](sase-n.2.md) ✓
- **Blocks:** [sase-n.4](sase-n.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e0d376f`](https://github.com/sase-org/sase/commit/e0d376fc95a4cc625c769279426d940509b9d90f) | ref: generalize LLM provider metadata via pluggy hooks (sase-n.3) | [sase-n.3](sase-n.3.md) | 2026-04-24 18:31:46 |

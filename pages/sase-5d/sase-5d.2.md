# Bead: sase-5d.2 — Phase 2 - Parser, Completion, Doctor, and Schema Migration

[Bead Pages](../README.md) / [sase-5d](README.md) / sase-5d.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5d.2`
**Created:** 2026-06-30 13:25:33 UTC · **Closed:** 2026-06-30 14:38:56 UTC
**Plan:** [202606/model\_alias\_configuration\_migration.md](https://github.com/sase-org/sase--plans/blob/main/202606/model_alias_configuration_migration.md)

## Notes

COMMIT: 9dcb2b585

[2026-07-27T21:38:01Z · sase-a1.land] [2026-06-30T14:35:51Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 implemented (parser, completion, doctor, schema migration).

DELIVERED:
- directives.py: _validate_model_alias_prefix error message now points at the new alias policy (configured/built-in aliases, e.g. @default, @coder) instead of 'the reserved worker/other'. Validation already routes through model_alias_names() from Phase 1.
- config.py: added EPIC_CREATOR_MODEL_ALIAS_NAME / EPIC_LANDER_MODEL_ALIAS_NAME / PHASE_WORKER_MODEL_ALIAS_NAME constants and rewired _ROLE_ALIAS_FALLBACKS to use them (single source of truth for role names, consumed by completion).
- model_completion.py: replaced the RESERVED_MODEL_ALIASES (@worker/@other) catalog entries with the implicit role aliases @default, @coder, one @<provider>_coder per registered provider (from the metadata payload's provider order), @epic_creator, @epic_lander, @phase_worker (kind=implicit_alias). Bare typed hints (e.g. codex_coder) still match and insert @codex_coder. A user-configured alias shadowing an implicit one is surfaced once with its real target. A user-defined worker/other is now an ordinary user alias.
- sase.schema.json: removed llm_provider.worker_models (additionalProperties:false now rejects it AND default_model); documented @alias references in the model_aliases description (kept as a string map).
- doctor checks_config.py: new config.model_aliases check warns on stale worker_models / default_model and on model_aliases values referencing retired (@worker/@other) or unknown @aliases; extended config.model_xprompts to flag xprompt directives still emitting retired @worker/@other with replacement guidance.
- Justfile: removed the pyvision --epic-symbol whitelist for coder_model_alias_for_provider (now consumed by completion); special_model_alias_names + role_model_directive_value remain for Phases 3-4.

RUST: verified sase-core xprompt LSP (crates/sase_xprompt_lsp/src/server.rs) parses model-catalog 'kind' as a free-form String with no enum validation, so the new implicit_alias kind needs no Rust change; catalog schema_version stays 1. No Rust regression required.

TESTS: updated test_xprompt_model_completion.py, test_config_schema.py (worker_models/default_model now rejected; @alias-map accepted), tests/doctor/test_checks_config.py (+config.model_aliases and retired-alias xprompt cases). Full suite green (14956 passed, 6 skipped).

DEFERRED (per plan): @worker/@other still resolve as legacy stubs (model_alias_names) and worker_models readers remain until Phase 3 (plan accept) and Phase 4 (bead/work + worker-lane UI) migrate the emit sites.

NOTE: pre-existing unrelated 'sase init --check skills' drift (sase_beads SKILL.md in chezmoi) fails just-check validate; not caused by this phase (verified via stash).

## Dependencies

- **Depends on:** [sase-5d.1](sase-5d.1.md) ✓
- **Blocks:** [sase-5d.3](sase-5d.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5d.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5d.2/README.md) | [sase-5d.2](sase-5d.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`829b43d`](https://github.com/sase-org/sase/commit/829b43d25ddf4a164cd0a44e88c9bf034a2c7805) | feat(llm\_provider)!: migrate alias parser, completion, doctor, and schema (sase-5d.2) | [sase-5d.2](sase-5d.2.md) | 2026-06-30 14:40:05 |

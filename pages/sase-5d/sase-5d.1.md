# Bead: sase-5d.1 — Phase 1 - Core Alias Resolver and Default Launch Semantics

[Bead Pages](../README.md) / [sase-5d](README.md) / sase-5d.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5d.1`
**Created:** 2026-06-30 13:24:59 UTC · **Closed:** 2026-06-30 14:13:16 UTC
**Plan:** [202606/model\_alias\_configuration\_migration.md](https://github.com/sase-org/sase--plans/blob/main/202606/model_alias_configuration_migration.md)

## Notes

COMMIT: 4b29802f9

[2026-07-27T21:37:58Z · sase-a1.land] [2026-06-30T14:11:02Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 1 implemented (additive core).

DELIVERED:
- config.py: centralized alias policy. New constants DEFAULT_MODEL_ALIAS_NAME, CODER_MODEL_ALIAS_NAME, PROVIDER_CODER_ALIAS_SUFFIX, _ROLE_ALIAS_FALLBACKS. Helpers default_model_alias_name(), coder_model_alias_for_provider(), role_model_directive_value(), special_model_alias_names() (+ private _role_/_provider_coder_ helpers). model_alias_names() now unions configured + special (default/coder/<provider>_coder/epic_creator/epic_lander/phase_worker) + legacy worker/other.
- resolve_model_alias(): follows @alias references in config values; resolves implicit specials (default -> configured-or-provider-tier-default; coder/<provider>_coder/epic_*/phase_worker -> @default chains) with cycle/depth protection.
- registry.py: registered_provider_names(); resolve_default_alias_provider_model(tier) (configured @default or provider tier default, override-agnostic).
- temporary_override.resolve_effective_default_provider_model(): override wins, else routes through @default. So run_agent_directives, _query, workflow_executor_steps_prompt all route no-directive launches through @default automatically.
- _invoke.invoke_agent(): no-directive path honors active override, else a configured @default alias (plain tier default unchanged so model_override stays None / [BIG] label preserved).
- Tests added in test_llm_provider_providers.py + test_llm_provider_invoke.py. Full suite green (14932 passed).

DEFERRED (intentional, per plan Task 6 'leave thin deprecated stubs only if needed by later phases'):
- @worker/@other NOT yet invalidated. Kept as functional deprecated stubs because Phase 3 (run_agent_exec_plan_accept emits @worker) and Phase 4 (bead/work.py emits @worker; worker-lane UI) still produce/use them. Phase 1 exit criterion '@worker/@other invalid' completes when those emit sites migrate to @phase_worker/@<provider>_coder. worker_models helpers + worker temporary-override + pre_override snapshot all retained for Phases 3-4.

JUSTFILE / pyvision: added --epic-symbol sase-5d(...) for special_model_alias_names (Phase 2 completion/doctor consumer), coder_model_alias_for_provider (Phase 3 plan accept), role_model_directive_value (Phase 4 bead work). REMOVE each entry when its phase wires up the real consumer.

NOTE: pre-existing unrelated 'sase init --check skills' drift (sase_beads SKILL.md) fails just-check validate; not caused by this phase (verified via stash).

## Dependencies

- **Blocks:** [sase-5d.2](sase-5d.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5d.1/README.md) | [sase-5d.1](sase-5d.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4d1a4b7`](https://github.com/sase-org/sase/commit/4d1a4b71ff832c07364f242848371a85dfa7a0e9) | feat(llm\_provider): add core alias resolver and @default launch semantics (sase-5d.1) | [sase-5d.1](sase-5d.1.md) | 2026-06-30 14:13:58 |

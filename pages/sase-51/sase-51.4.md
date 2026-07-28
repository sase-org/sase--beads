# Bead: sase-51.4 — Phase 4: Compatibility Audit And Deprecation Guardrails

[Bead Pages](../README.md) / [sase-51](README.md) / sase-51.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-51.4`
**Created:** 2026-06-20 17:53:30 UTC · **Closed:** 2026-06-20 20:34:34 UTC
**Plan:** [202606/linked\_repos\_rename\_codex.md](https://github.com/sase-org/sase--plans/blob/main/202606/linked_repos_rename_codex.md)

## Notes

COMMIT: d5f3fca92

[2026-07-27T21:36:28Z · sase-a1.land] [2026-06-20T20:29:14Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 4: Compatibility Audit And Deprecation Guardrails — COMPLETE.

DECISION (non-fatal warning for legacy sibling_repos):
Added a non-fatal deprecation surface via the EXISTING config-layer diagnostics
(`sase config layers` + `sase doctor` config.layers check), deliberately NOT the
per-agent runtime resolution path. Rationale: launch_spawn / run_agent_phases /
run_agent_runner_setup re-resolve linked repos on every agent launch, so emitting
a warning there would create the "noisy repeated warnings in launched agents" the
phase warns against. The diagnostics are user-invoked, so the nudge shows once
when a user inspects config. Impl: DEPRECATED_TOP_LEVEL_KEYS={"sibling_repos":
"linked_repos"} + _ConfigLayer.deprecated_keys (mirrors UNSUPPORTED_TOP_LEVEL_KEYS).
Doctor now WARNs with "deprecated keys (rename): sibling_repos -> linked_repos".

STALE PUBLIC VOCABULARY FIXED:
- src/sase/main/workspace_handler_context.py: user-facing RuntimeError + docstring
  "Configured sibling repo" -> "Configured linked repo" (kept the `sibling`
  ProjectSpec lifecycle state name; clarified it's legacy backing state).
- docs/project_spec.md + docs/configuration.md: `sibling` state described as
  "configured linked repository" bookkeeping / legacy backing state name; updated
  `sase workspace open -p <sibling>` -> `<linked_repo>` placeholders.
- Justfile rust-check comment: "sibling repo absent" -> "linked repo absent".

AUDIT (rg for sibling_repos, SASE_SIBLING_REPOS_JSON, SASE_SIBLING_REPO_,
opened_siblings.json, "sibling repo") — all remaining live hits are deliberate:
- Compat aliases: src/sase/linked_repos.py (SIBLING_* env/marker/config-key
  consts, dual-write, conflict-warning), src/sase/sibling_repos.py wrapper,
  config/sase.schema.json deprecated alias key, agent_meta["sibling_repos"] alias
  (run_agent_directives/runner_setup), Justfile SASE_SIBLING_REPO_* fallbacks.
- Internal identifiers: commit_finalizer_state/prompting/.py (params, funcs,
  kind="sibling"). User-facing finalizer prompt text already says "linked repo".
- Deprecation docs: README.md, docs/configuration.md, docs/init.md, docs/editor.md.
- Unrelated meanings (kept per epic scope): path-layout ../sase-* checkouts
  (docs/rust_backend.md, docs/xprompt.md, sase.yml cross_repo_impact, memory),
  the `sibling` ProjectSpec state, ChangeSpec .gp/.sase siblings, agent siblings.
- sdd/** and tests/** hits are historical records / compat tests (left as-is).

NOT TRIGGERED: generated skills / CLI-skill contract files do not reference the
configured-repo feature, so memory/generated_skills.md read was not required.

DEFERRED (approval-gated): sase.yml:63 cross_repo_impact memory-gen text still
says "maintained sibling repos (../sase-*)" — path-layout wording feeding
generated memory; left unchanged (memory generation source is approval-gated and
this is path-layout, not feature, vocabulary).

TESTS: added test_config.py deprecated/canonical key tests + doctor
test_config_layers_warns_on_deprecated_sibling_repos. `just check`: lint/mypy/fmt
green; 12739 passed. The only failures (10) are pre-existing in
tests/test_directives_split_alternatives.py (sase-52 %{...} brace feature,
verified failing on clean tree b0f316ab7) — unrelated to this phase.

[2026-07-27T21:36:32Z · sase-a1.land] [2026-06-20T20:35:08Z · bryanbugyi34@gmail.com] (restored 2026-07-27) COMMIT: 81eaec1a7

## Dependencies

- **Depends on:** [sase-51.3](sase-51.3.md) ✓
- **Blocks:** [sase-51.5](sase-51.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-51.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-51.4/README.md) | [sase-51.4](sase-51.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d5f3fca`](https://github.com/sase-org/sase/commit/d5f3fca9269bf7cbb9bb3e08826bcccc513ac439) | feat(config): warn on deprecated sibling\_repos key (sase-51.4) | [sase-51.4](sase-51.4.md) | 2026-06-20 20:37:08 |

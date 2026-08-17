# Bead: sase-ns.6.6.2 — Reconcile the two generated-memory drift checkers (sase-n0)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.2` · **Size:** medium
**Created:** 2026-08-17 04:03:10 EDT · **Closed:** 2026-08-17 04:21:13 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

memory_check: make `sase validate`'s memory step and `sase init memory --check` resolve the same template source for the same generated note so they cannot give opposite answers on one tree, and add a regression gate; leave a `TASK NEEDS APPROVAL` note rather than editing or regenerating any memory file content.

## Notes

[2026-08-17T08:20:46Z · sase-ns.6.6.2] PROPOSED FOLLOW-UP: the global `sase` on PATH (/home/bryan/.local/bin/sase, a uv tool install) is editable-installed against a separate checkout (~/projects/github/sase-org/sase, confirmed via sase.__file__ and a missing `flag` subcommand this workspace's own .venv/bin/sase has). just check's validate recipe pins to {{venv_bin}}/sase so it always matches the workspace tree, but an agent typing a bare `sase init memory --check` hits that separate, independently-versioned install instead, comparing this workspace's committed files against a different checkouts templates. This plausibly explains the repeated cross-agent memory-drift disagreements reported for sase-n0/sase-i7 even though no generator code divergence exists. Worth a task bead to decide whether to keep the global tool install synced (e.g. a chezmoi/reinstall hook) or document that ad hoc bare `sase` memory-drift checks are unreliable outside just check.

[2026-08-17T08:21:13Z · sase-ns.6.6.2] Structural finding (code, not inferred from a green run): sase validate's memory step and sase init memory --check / sase memory init --check are not two divergent checkers but literally one — validate_handler.py shells out to `$sys.executable -m sase init memory --check` as a subprocess, and both that path and the direct CLI both funnel through plan_init_memory -> _memory_root_plans -> plan_memory_root -> memory_root_context -> render_expected_memory_files()/provider_shim_plan(). No generator-level divergence exists in source, so per the plan's stated fallback ('if they genuinely resolve the same source today, say so with the code evidence, and the phase's remaining deliverable is the regression gate') no reconciliation edit was made and no memory-content approval boundary was hit. Added the required regression gate: tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output plans this repo's real project-scoped memory tree hermetically (scratch HOME/CONFIG_DIR, use_chezmoi=False, real_directory_map_assets fixture) and asserts zero drift actions/blockers against the committed files, so a future generator/template mismatch fails just check's scoped test lane directly rather than surfacing only via a manual sase validate run. Verified it currently passes (no live drift). Alias vocabulary determined: @<size> (@xsmall/@small/@medium/@large/@xlarge) is authoritative in both src/sase/default_config.yml and the committed sase/memory/sase_sizes.md; _worker-suffixed names exist only as retired/removed aliases in sase doctor's config-alias migration guidance (checks_config_common.py, checks_config_model_aliases.py), unrelated to the memory generator. Filed a PROPOSED FOLLOW-UP on this bead about a likely real-world mechanism for the originally reported disagreement: the global uv-tool-installed sase on PATH points at a separate checkout from any given ephemeral workspace. just check is green (fmt/lint/SASE validation/committed plans/scoped tests, including the new regression test).

[2026-08-17T08:21:50Z · sase-ns.6.6.2] Confirmed sase validate's memory-drift check runs init memory --check as a subprocess (same code path, not divergent generators); both funnel through render_expected_memory_files/provider_shim_plan. Added tests/main/test_init_memory_committed_drift.py as a regression gate comparing generator output to committed memory files. Verified _worker-suffixed aliases only exist as retired names in sase doctor migration guidance, not in active config/templates. just check passed (fmt, lint, validation, scoped tests).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.2/README.md) | [sase-ns.6.6.2](sase-ns.6.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`99b4e43`](https://github.com/sase-org/sase/commit/99b4e43a15fc558c96896b63e8807b51e9fec878) | test: add regression gate for committed memory-file drift | [sase-ns.6.6.2](sase-ns.6.6.2.md) | 2026-08-17 04:22:31 EDT |

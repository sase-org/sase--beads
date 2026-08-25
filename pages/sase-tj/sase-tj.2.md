# Bead: sase-tj.2 — Textual-free agent catalog row model

[Bead Pages](../README.md) / [sase-tj](README.md) / sase-tj.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0da](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0da.md) · **Assignee:** `sase-tj.2` · **Size:** medium
**Created:** 2026-08-25 08:09:38 EDT · **Closed:** 2026-08-25 08:58:59 EDT
**Plan:** [202608/artifacts\_agents\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_agents_pane.md)

## Description

catalog: build the registry-spined, index-enriched catalog snapshot as a widget-free module shared by the pane and the CLI, with a measured budget.

## Notes

[2026-08-25T12:57:43Z · sase-tj.2] PATCH FIELD MEASUREMENT (§3.4): kept the patch field on AgentCatalogRow. Measured on this machine: dismissed-archive meta_patch has 77 distinct values across 6,840 top-level summaries (mostly singleton run-scoped names, not project keys); artifact-index cl_name has ~56 distinct values across 8,047 rows, dominated by project keys (gh_sase-org__sase 7,234/8,047) but with a meaningful non-project-key tail (e.g. sase_fix_just_linters_14, sase_recent_bug_audit_sase_*). Neither is degenerate. derive_patch() in _derive.py prefers meta_patch over cl_name and excludes values matching known_project_keys() (from sase.core.project_lifecycle_facade.list_project_records, currently-enabled projects only).

[2026-08-25T12:58:05Z · sase-tj.2] PROPOSED FOLLOW-UP: just check fails on lint (symvision) at current master tip (1fe598e2d) — FinalizerBaselineRecord in src/sase/llm_provider/commit_finalizer_baseline.py is public but only used within its own defining file. Confirmed pre-existing and unrelated to this phase by stashing this phase's new files and re-running just _lint-symvision on the clean tree — same failure. Introduced by a prior commit on this branch (1fe598e2d or 2f9c4ae29), not by sase-tj.2. File as a bug task bead so an unrelated agent's just check stops going red.

[2026-08-25T12:58:27Z · sase-tj.2] PROPOSED FOLLOW-UP: known_project_keys() in _derive.py (used by derive_patch, §3.4) only covers currently-enabled projects via list_project_records(sase_projects_dir()) — an archived, disabled, or renamed project key can still slip through derive_patch() as a false "patch" value. Documented as a known gap in known_project_keys()'s docstring. The dialect phase (or a later one) should decide whether this needs a more complete historical project-key source before shipping the patch: query field to users.

[2026-08-25T12:58:59Z · sase-tj.2] Built src/sase/agents/catalog/ (Textual-free, no Textual imports — verified). Modules: _models.py (AgentCatalogRow/AgentCatalogSnapshot, frozen+slots dataclasses), _family.py (name-based family/role derivation), _sources.py (projected raw-SQL artifact-index reader excluding record_json; dismissed-archive top-level + targeted child-only-suffix fallback reader), _derive.py (kind/revivable/attention/retry/patch derivation), _build.py (orchestration + 0-ambiguous join assertion), __init__.py (promotion-trigger docstring per §2.5). Verified: join is 0-ambiguous (raises AgentCatalogBuildError on a synthetic duplicate raw_suffix, tests/test_agent_catalog.py::TestJoinInvariants); fixtures for solo/family/clan/member/owner-qualified-name/collision-history/workflow-child/name-only-thin-row all pass (25 tests total in tests/test_agent_catalog.py); never SELECT * / never record_json (explicit test + column list). Bench: tests/perf/bench_agent_catalog.py builds a 12,525-entry synthetic corpus (real registry write + real artifact-index sqlite; dismissed-archive loaders dependency-injected since faithfully reproducing that on-disk index at scale is unrelated setup cost) and asserts <=400ms — measured ~160-186ms median, well under budget. patch field: kept (measurement noted on bead — 77 distinct meta_patch, ~56 distinct cl_name, not degenerate). just install + just check green except a pre-existing, unrelated symvision failure (FinalizerBaselineRecord in commit_finalizer_baseline.py) confirmed present on the clean tree with this phase's files stashed out — filed as PROPOSED FOLLOW-UP, not fixed here. ruff/mypy clean on all new files. No --epic-symbol entries for this bead.

## Dependencies

- **Blocks:** [sase-tj.4](sase-tj.4.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tj.8](sase-tj.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tj.2/README.md) | [sase-tj.2](sase-tj.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a0c7d6`](https://github.com/sase-org/sase/commit/2a0c7d6fa8593ab1758117a8ed59cb0a13b5f3b2) | feat(agents): add Textual-free agent catalog row model | [sase-tj.2](sase-tj.2.md) | 2026-08-25 09:00:01 EDT |

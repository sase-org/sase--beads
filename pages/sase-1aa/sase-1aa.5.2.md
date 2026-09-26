# Bead: sase-1aa.5.2 — Replace stale model and pool enumerations with generated-table links

[Bead Pages](../README.md) / [sase-1aa.5](sase-1aa.5.md) / sase-1aa.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aa.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aa.land.md) · **Assignee:** `sase-1aa.5.2` · **Size:** medium
**Created:** 2026-09-26 08:43:41 EDT · **Closed:** 2026-09-26 09:19:14 EDT
**Plan:** [202609/finish\_model\_catalog\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_model_catalog_landing.md)

## Description

refresh_prose: remove the duplicate manual model list and rewrite current-value prose that would go stale after a manifest-only catalog or alias retune.

## Notes

[2026-09-26T13:18:45Z · sase-1aa.5.2] PROPOSED FOLLOW-UP: just check lint (symvision) fails on stale --epic-symbol entries for closed beads sase-19x.4/sase-19f/sase-18i; reproduces identically on clean base tree, triage verdict KNOWN (witness 3734c902fe084b367d9982aaf639c038)

[2026-09-26T13:19:14Z · sase-1aa.5.2] refresh_prose done: removed duplicate Automatic Provider Resolution table in docs/llms.md (now links to generated Built-in Model Catalog); rewrote pool-membership/tier/fallback pins in docs/llms.md, agent_providers.md, configuration.md, README.md, getting_started.md, ace.md to point at generated tables. Verified: fmt-docs-check pass, fmt-md-check pass, model-policy-check pass, ruff/mypy/keep-sorted pass, test_render_model_docs.py + test_contract_manifest.py pass. symvision lint failure is pre-existing on clean tree (recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-1aa.5.3](sase-1aa.5.3.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aa.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aa.5.2/README.md) | [sase-1aa.5.2](sase-1aa.5.2.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec25a1a`](https://github.com/sase-org/sase/commit/ec25a1a3338edf683336138a6e6819f7a5906ffa) | feat: eplace stale model and pool enumerations with generated-table links (sase-1aa.5.2) | [sase-1aa.5.2](sase-1aa.5.2.md) | 2026-09-26 09:25:59 EDT |

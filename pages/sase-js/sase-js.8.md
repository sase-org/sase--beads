# Bead: sase-js.8 — The sase-research plugin repository

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.8` · **Size:** large
**Created:** 2026-08-11 13:23:38 EDT · **Closed:** 2026-08-11 17:02:40 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

research: build `sase-org/sase-research` as an installable plugin owning the `research` ref provider, the `research-highlights` file-hook provider, and the `#research*` xprompts, with wheel-level CI, tests, and documentation.

## Notes

[2026-08-11T21:02:17Z · sase-js.8] PROPOSED FOLLOW-UP: sase.artifact_providers has a latent circular-import fragility on a fresh interpreter -- importing sase.artifact_providers (or assemble_artifact_provider_registry) as the very first sase submodule raises 'ImportError: cannot import name ArtifactRefProviderRegistry from partially initialized module sase.artifact_providers.registry', because sase.config.file_hooks imports sase.artifact_providers.registry while sase.config is still initializing. Importing sase.config first works around it. Discovered while writing sase-research's contract tests (tests/conftest.py works around it); worth a root-cause fix in sase core's import ordering.

[2026-08-11T21:02:40Z · sase-js.8] Built sase-org/sase-research end to end per the approved plan: hatchling src/ layout; RESEARCH_REF_PROVIDER (schema_version 1, kind research, inventory 20*/**/*.md, frontmatter properties create_time/updated_time/status/tags, vcs_permalink + markdown_table publication) and RESEARCH_HIGHLIGHTS_HOOK (research-highlights, sidecars:[research], path_globs 20*/**/*.md + !20*/*/*__*.md, agent_name_globs excluding research.*.cld/cdx, ops:[ADD], timeout 120s, command deliberately unset + required) registered as separate sase_artifact_refs/sase_file_hooks pluggy hookimpl objects (avoids the double-registration gotcha since the registry calls both hookspec methods on every discovered plugin). Lifted #research, #research/image, #research/more, #research/prompt, and the 4-segment #research_swarm plus model aliases/bucket/tribe verbatim from chezmoi without touching it; dropped old_research_swarm per plan. 27 contract tests (registry discovery+provenance, duplicate-kind diagnostic, use:-vs-inline digest parity, missing-provider fail-soft, required-command fail-soft, ref/hook glob divergence via the real Rust path filter, frontmatter typing, xprompt swarm segment/dependency graph, default-config schema validation, CI-shape assertions) plus 3 wheel-contract tests (sdist/wheel member lists, fresh-venv install with source-overridden sase + coordinated maturin sase-core-rs build, all 4 entry points + both provider specs + defaults + all 5 xprompts discoverable) all pass. just check (ruff+mypy+pytest) is green. CI (ci.yml/publish.yml) coordinates against sase and sase-core source checkouts via a uv --overrides file, since sase>=0.17.0 (the floor with the provider registry) has not reached PyPI yet. README/GitHub description disambiguate sase-research from sase--research. Worktree contains only this phase's intended files.

[2026-08-11T21:03:49Z · sase-js.8] Verified: just check green (ruff+mypy+pytest, 27 fast contract tests passing); wheel-contract test built sdist/wheel, installed into a fresh venv, and confirmed all 4 entry-point groups (sase_artifact_refs, sase_file_hooks, sase_xprompts, sase_config) plus default_config.yml and all 5 Markdown xprompts resolve from the installed wheel without the source tree. Registry discovery/provenance, duplicate/missing-provider diagnostics, required-command resolution, and use:-vs-inline digest parity all pass. Working tree contains only this phase's intended files. README/docs/GitHub description disambiguate sase-research (plugin) from sase--research (content sidecar).

## Dependencies

- **Depends on:** [sase-js.3](sase-js.3.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-js.9](sase-js.9.md) ✓ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.8.md) | [sase-js.8](sase-js.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research | [`sase-research@f499469`](https://github.com/sase-org/sase-research/commit/f499469a39ea5fbf52d3b75a92ac65ae5eba8c37) | feat: scaffold the sase-research plugin package | [sase-js.8](sase-js.8.md) | 2026-08-11 17:04:36 EDT |

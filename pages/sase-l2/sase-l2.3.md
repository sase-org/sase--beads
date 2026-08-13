# Bead: sase-l2.3 — Verify the catalog cutover and restore the plugin

[Bead Pages](../README.md) / [sase-l2](README.md) / sase-l2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zt](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zt.md) · **Assignee:** `sase-l2.3` · **Size:** small
**Created:** 2026-08-13 14:12:20 EDT · **Closed:** 2026-08-13 15:08:13 EDT
**Plan:** [202608/research\_artifacts\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/research_artifacts_rename.md)

## Description

integration-cutover: refresh the live catalog, exercise linked-repository and install resolution, install the renamed plugin from Git, and prove the old distribution identity is absent while the existing research contracts work.

## Notes

[2026-08-13T19:07:42Z · sase-l2.3] PROPOSED FOLLOW-UP: Remove stale symvision epic-symbol whitelist entries for closed bead sase-kz.5 — just check fails in lint (symvision) before the scoped test lane because the whitelist still contains symbols tied to closed bead sase-kz.5.

[2026-08-13T19:08:13Z · sase-l2.3] Verified live catalog refresh has one research-artifacts built-in entry (sase-org/sase-research-artifacts) and no sase-research entry; dry-run index resolves to distribution sase-research-artifacts and dry-run --git resolves to git+https://github.com/sase-org/sase-research-artifacts; installed research-artifacts from Git, axe restarted, plugin list/show reports sase-research-artifacts 0.1.0 with artifact-ref/config/file-hook/xprompt entry points; import metadata and uv receipt contain new distribution/Git URL and no exact old sase-research distribution; repo list/open resolves linked repo sase-research-artifacts with env SASE_RESEARCH_ARTIFACTS and no old linked row; doctor -C config.repos OK; @research resolved research:202602/sase_plugin_specifics.md exactly; research-highlights file hook and #research* xprompts loaded from the renamed plugin. Ran just install; just check passed fmt/keep-sorted/ruff/mypy/pyscripts/test-waits/changelog/patch-stitch lints, then failed on unrelated stale symvision whitelist entries for closed bead sase-kz.5; recorded PROPOSED FOLLOW-UP on this bead.

## Dependencies

- **Depends on:** [sase-l2.1](sase-l2.1.md) ✓ · ⧖ 2026-08-13
- **Depends on:** [sase-l2.2](sase-l2.2.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l2.3/README.md) | [sase-l2.3](sase-l2.3.md) | 0 |

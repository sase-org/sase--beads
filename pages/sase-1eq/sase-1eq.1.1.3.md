# Bead: sase-1eq.1.1.3 — Add canonical macro sources and legacy loading policy

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.3` · **Size:** medium
**Created:** 2026-10-02 07:55:50 EDT · **Closed:** 2026-10-02 10:47:28 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

catalog-sources: Add canonical macro layouts and source lists beside untouched legacy layouts; load new-first package/plugin/home/project paths and transport variables. Thread default-true accept_legacy_xprompt_names through core and Python catalog entry points, rejecting retired definition sources when false while preserving skills and memory placement. Cover explicit resource precedence and option aliases.

## Notes

[2026-10-02T14:47:04Z · sase-1eq.1.1.3] catalog-sources evidence: content_layout adds macros to project/home/chezmoi (canonical sase/macros; chezmoi legacy dot_macros/dot_xprompts/xprompts) and macro_sources new-first (3 canonical + 8 retired + 6 config + 6 symbolic with entrypoint:sase_macros/macros, package:macros, package:macros/steps, package:default_macros; skill locators entrypoint:sase_macros/skills, package:macros/skills added, legacy lists byte-identical); loader probes macros before xprompts/default_macros before default_xprompts/macros-skills before xprompts-skills with explicit-beats-inferred and SASE_MACRO_ new-first envs (PACKAGE/BUILTIN/DEFAULT/PLUGIN_DIRS/CONFIG_PATHS); accept_legacy_xprompt_names default-true threaded via CatalogLoader/Options/ResourcePaths, PyO3 options dict + snippet binding, false skips retired dirs/resources incl explicit/plugin while skills/memory/config stay; tests: 10 new catalog_sources + 2 layout + 1 PyO3 alias/duplicate tests, 42 macro_catalog + 17 layout green; residual xprompt hits are emission pins/aliases/legacy-reader tests/unchanged LSP/protected contracts with // legacy xprompt spelling on new retired constants; tool runs: 51c4b59d (clippy derivable_impls, fixed), 4d3c96f0 (provider_priority load flake, passes alone), 02303494489af8099ff6e21461b4eeeb succeeded

[2026-10-02T14:47:28Z · sase-1eq.1.1.3] catalog-sources done: sase tool run check 02303494489af8099ff6e21461b4eeeb succeeded (fmt/features/clippy/workspace+PyO3/LSP/script tests); targeted content_layout 17 + macro_catalog 42 + PyO3 alias test pass; canonical sase/macros layouts + macro_sources new-first with legacy xprompt_sources byte-identical; SASE_MACRO_ new-first envs and package_macros/default_macros/plugin_macro_dirs aliases with duplicate rejection; accept_legacy_xprompt_names defaults true, false skips retired incl explicit/plugin while skills/memory/config stay; epic-symbols empty

## Dependencies

- **Depends on:** [sase-1eq.1.1.2](sase-1eq.1.1.2.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.1.1.4](sase-1eq.1.1.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.3/README.md) | [sase-1eq.1.1.3](sase-1eq.1.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4f0bfd3`](https://github.com/sase-org/sase-core/commit/4f0bfd33e70b2a347d555a427f00a47fcc83bd11) | feat(core-expand): add canonical macro sources and legacy loading policy | [sase-1eq.1.1.3](sase-1eq.1.1.3.md) | 2026-10-02 10:49:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.1.1.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.3/README.md

<!-- sase:referenced-by:end -->

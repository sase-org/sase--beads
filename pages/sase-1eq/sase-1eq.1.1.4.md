# Bead: sase-1eq.1.1.4 — Accept macro definition keys and permanent directive aliases

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.4` · **Size:** medium
**Created:** 2026-10-02 07:55:51 EDT · **Closed:** 2026-10-02 11:24:34 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

authored-inputs: Accept macros keys in all YAML/frontmatter/config loading and editor paths, diagnose duplicate spellings and retired authored keys, support both literal-zone directive families including mixed markers, and emit both local-definition child environment variables. Keep legacy presentation and output unchanged.

## Notes

[2026-10-02T15:24:12Z · sase-1eq.1.1.4] authored-inputs done in sase-core @4f0bfd3+14 files: macros:/xprompts: presence-based dual keys in config/project-local/markdown-frontmatter/YAML-workflow/nested-entry parsing (authored_macro_sections; DuplicateAuthoredKeys/RetiredAuthoredKey(naming macros)/MalformedAuthoredSection errors; legacy single-key stays lenient); frontmatter macros key + duplicate_macro_frontmatter_section error; diagnostics merge canonical-wins; macros_enabled alias canonicalized to xprompt_enabled (emitted contract unchanged) + mixed literal-zone markers; SASE_AGENT_LOCAL_MACROS==SASE_AGENT_LOCAL_XPROMPTS; definition_range probes macros-first; plugin macro dirs resolve first. Residual xprompt hits (~1882 lines): emission pins (diagnostic codes/directive name/env/serialized keys), input aliases, legacy-reader tests, protected contracts/fixtures, unchanged LSP package/cmds (lsp-inputs phase), durable filenames (durable-readers phase), history. No new root exports/prelude aliases. Evidence: sase tool run check 4f53fb19c38808d9cf709a2748cb26b3 exit 0 (190s); targeted macro_catalog 52/editor 411/agent_launch 209/py-editor_completion 27 green.

[2026-10-02T15:24:34Z · sase-1eq.1.1.4] authored-inputs verified: sase tool run check 4f53fb19 exit 0 (fmt/clippy/workspace+PyO3/LSP/script tests); targeted macro_catalog 52, editor 411, agent_launch 209, py editor_completion 27 green incl 18 new authored-inputs tests (old/new/both-key/false-policy/nested/mixed-marker/env-parity); legacy presentation+output unchanged; epic-symbols empty

## Dependencies

- **Depends on:** [sase-1eq.1.1.3](sase-1eq.1.1.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.1.1.5](sase-1eq.1.1.5.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.4/README.md) | [sase-1eq.1.1.4](sase-1eq.1.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e6a3452`](https://github.com/sase-org/sase-core/commit/e6a3452f7134efe6a805e099a3f19ddfb918fb50) | feat(core-expand): accept macro authored keys and permanent directive aliases | [sase-1eq.1.1.4](sase-1eq.1.1.4.md) | 2026-10-02 11:26:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.1.1.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.4/README.md

<!-- sase:referenced-by:end -->

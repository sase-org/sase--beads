# Bead: sase-1eq.10 — sase-core contract flip with same-turn pin bump

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.10` · **Size:** large
**Created:** 2026-10-02 06:51:33 EDT · **Closed:** 2026-10-05 07:33:31 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

core-flip: make sase-core emit only macro spellings and remove the legacy binding names. Rename the LSP crate, bump the index and wire schemas, and add the mobile macros route. In the same declared turn, update sase mirrors and pin, and the chezmoi LSP install script.

## Notes

[2026-10-05T03:01:46Z · sase-1eq.5.1.land] From the sase-1eq.5.1 (TUI macro surfaces) landing, 2026-10-04: sase-side pre-flip adapters that core-flip must flip in its same declared turn. These were deferred per plan and recorded as PROPOSED FOLLOW-UP by sase-1eq.5.1.5 (notes #1, #3) and sase-1eq.5.1.6 (note #1). (1) The Jinja scope kind: src/sase/macro/jinja_assist.py JinjaScopeKind = Literal['prompt', 'xprompt'], plus LEGACY_XPROMPT_JINJA_SCOPE_KIND in src/sase/legacy_xprompt_names.py, used by ace/tui actions/agent_workflow/_prompt_bar_save_macro.py, widgets/_local_macro_conversion.py, and widgets/_prompt_input_bar_frontmatter.py. (2) The completion spacer binding: legacy_xprompt_names.require_legacy_xprompt_completion_spacer_binding, called from ace/tui/widgets/_argument_syntax_editing.py. (3) The MacroArgumentSource dual reader: 'xprompt' in src/sase/macro/highlight.py _SOURCES and line ~510. (4) The detail-header xprompts_used response field, pinned in tests/perf/bench_detail_header_summary.py. (5) Stats response keys, still read through mirror constants (request keys already send macro_*). The matching terminology-guard rows point at sase-1eq.10 in tests/_macro_terminology_strings.py and the pair tables; drop them when the wire flips.

## Dependencies

- **Blocks:** [sase-1eq.11](sase-1eq.11.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.5](sase-1eq.5.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.7](sase-1eq.7.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.8](sase-1eq.8.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.9](sase-1eq.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.10.md) | [sase-1eq.10](sase-1eq.10.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0279de6`](https://github.com/sase-org/sase-core/commit/0279de6b00a6c053fb82e0375f3c17469f581ab8) | feat(macros): flip emitted wires to macro spellings, rename LSP crate | [sase-1eq.10](sase-1eq.10.md) | 2026-10-05 00:20:07 EDT |
| sase | [`dc8aee0`](https://github.com/sase-org/sase/commit/dc8aee0fbc4f9838dac4dd4d1d04b5137fbca4cf) | feat(macros): core\_flip WIP python mirrors for macro wires | [sase-1eq.10](sase-1eq.10.md) | 2026-10-05 00:24:32 EDT |
| chezmoi | [`chezmoi@50ff3b0`](https://github.com/bbugyi200/dotfiles/commit/50ff3b078278e417b8fb9e2a6d7fc3ff73c71273) | feat(macros): install sase-macro-lsp, drop stale xprompt binary | [sase-1eq.10](sase-1eq.10.md) | 2026-10-05 00:28:59 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.5.1.land][1] | Confirm core-flip owns the JinjaScopeKind, completion spacer binding, xprompts_used, and stats response wires left by sase-1eq.5.1 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.5.1.land/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1eq.1.1 — Finish the additive Rust macro rename and close sase-1eq.1

[Bead Pages](../README.md) / [sase-1eq.1](sase-1eq.1.md) / sase-1eq.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.land`
**Created:** 2026-10-02 07:55:46 EDT · **Closed:** 2026-10-02 15:24:02 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/finish_core_macro_expand.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md

<!-- sase:links:end -->

## Description

Complete all remaining core-expand contracts, prove compatibility with unchanged sase, and close only the original phase after its child epic lands.

## Notes

[2026-10-02T18:53:24Z · sase-1eq.1.1.land] LAND TRIAGE (sase-1eq.1.1.land): phase sase-1eq.1.1.7 PROPOSED FOLLOW-UP note #2 split into two outcomes. (1) DECLINED as a follow-up and kept as EPIC WORK: 4 of the 5 'KNOWN pre-existing' sase check failures are caused by this epic. They are test_runtime_directive_vocabulary_matches_core_contract, test_directive_completion_matches_aliases_to_canonical_insertions, test_ctrl_t_at_alias_partial_inserts_canonical_directive, and test_percent_partial_auto_opens_directive_panel. Commit e6a3452f (phase 1.1.4) set DIRECTIVES xprompts_enabled alias: Some("macros_enabled"), which changes the emitted directive_contract row (alias null -> macros_enabled). Unchanged sase on the old pin then gains an extra contract alias, and %m matches xprompts_enabled, so Ctrl-T no longer completes %model. Reproduced on 2026-10-02 against core 29da6fb7 rebuilt into unchanged sase e34386fee4: 1 failed in the contract file, 3 failed in the completion files. 'Clean base' stash checks cannot clear a core-caused failure. The fix belongs in core: a hidden input-only directive alias, not a Python _DIRECTIVE_ALIASES sync, which would change the unchanged tree. Planned as the landing tale. (2) test_empty_panel_escape_follows_the_hide_panel_binding is not caused by the epic (passes in isolation; multi-workspace KNOWN witnesses). No existing task covered it, so I created flake task sase-1ew (related link to sase-1al). Also noted: phase 1.1.3's provider_priority load flake (ToolRun 4d3c96f0) was not a PROPOSED FOLLOW-UP and is already tracked by sase-yn. No other PROPOSED FOLLOW-UP entries exist on phases 1.1.1-1.1.6.

[2026-10-02T19:23:44Z · sase-1eq.1.1.land] Hidden macros_enabled alias fix: restored DIRECTIVES xprompts_enabled alias to None and added HIDDEN_DIRECTIVE_ALIASES [(macros_enabled,xprompts_enabled)] with canonical_directive_name fallback; completion/contract no longer emit macros_enabled. Core gate sase tool run check 7b1c0f18ed641d6fb40c63a14fe84103 succeeded. rust-dev-install rebuilt linked core 29da6fb7+dirty into unchanged sase e34386fee4; sase_core_rs directive_contract xprompts_enabled alias None, no macros_enabled name/alias. sase focused: 74 passed (contract+parity+candidates+interactions), 41 passed (content_layout+core_health+xprompt_catalog+snippet_catalog); 4 repaired nodes pass.

[2026-10-02T19:24:02Z · sase-1eq.1.1.land] All seven phases verified against their commits (015ce7f6 base, then c4444abb, 421324bf, 4f0bfd33, e6a3452f, 926edfb8, be86aa9f, and 29da6fb7 in sase-core); this tale hidden-alias fix (xprompts_enabled alias None + HIDDEN_DIRECTIVE_ALIASES fallback) with core gate ToolRun 7b1c0f18ed641d6fb40c63a14fe84103; rust-dev-install of linked core 29da6fb7+dirty into unchanged sase e34386fee4 with sase_core_rs from linked checkout and xprompts_enabled alias None; four repaired sase nodes passing (test_runtime_directive_vocabulary_matches_core_contract, test_directive_completion_matches_aliases_to_canonical_insertions, test_ctrl_t_at_alias_partial_inserts_canonical_directive, test_percent_partial_auto_opens_directive_panel) plus focused counts 74 passed and 41 passed; all four binding pairs resolve and agree (resolve_macro/xprompt_skill_definition, macro/xprompt_skill_definition_wire_schema_version=1, macro/xprompt_argument_spans, prompt/xprompt_proc_origin=xprompt-proc); both LSP binaries build and answer --version (sase-macro-lsp 0.36.3, sase-xprompt-lsp 0.36.3); follow-ups from LAND TRIAGE: 4 failures fixed as epic work, flake task sase-1ew created, provider_priority flake already tracked by sase-yn.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.1.land.md) | [sase-1eq.1.1](sase-1eq.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f3818f8`](https://github.com/sase-org/sase-core/commit/f3818f817c20acc3ddc3955b2548709811dcf71f) | feat(directive): keep legacy directive contract byte-identical with hidden macros\_enabled alias | [sase-1eq.1.1](sase-1eq.1.1.md) | 2026-10-02 15:43:19 EDT |
| sase--plans | [`sase--plans@34151dc`](https://github.com/sase-org/sase--plans/commit/34151dcf6741964e799f91da126e0fdd10016ff7) | chore(plans): mark finish\_core\_macro\_expand epic plan done | [sase-1eq.1.1](sase-1eq.1.1.md) | 2026-10-02 15:47:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.1.1.2--1][1] | Need parent epic scope for phase close | 1 |
| read-by | [agent:sase-1eq.1.1.3][2] | Need parent epic scope | 1 |
| read-by | [agent:sase-1eq.1.1.6][3] | need parent epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.1.2.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.6/README.md

<!-- sase:referenced-by:end -->

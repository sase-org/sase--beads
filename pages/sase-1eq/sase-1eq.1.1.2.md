# Bead: sase-1eq.1.1.2 — Rename runtime wires and normalize prompt proc aliases

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.2` · **Size:** medium
**Created:** 2026-10-02 07:55:49 EDT · **Closed:** 2026-10-02 09:56:51 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

runtime-wire-names: Rename scan/statistics/launch/proc and remaining runtime internals with legacy serialization pins and new request aliases. Normalize prompt-proc inputs, add prompt_proc_origin, and complete root/prelude cleanup. Preserve index schemas, contracts, parity expectations, and emitted diagnostics.

## Notes

[2026-10-02T13:56:28Z · sase-1eq.1.1.2--1] Implementation: renamed UsedXPromptWire->UsedMacroWire, AgentXPrompt{StatsWire,StatsRowWire,FocusWire}->AgentMacro*, XpromptProcMetaWire->PromptProcMetaWire, stat/request fields to macro_top_n/macro_breakdown_top_n/macro_focus/used_macros/local_macros_file/prompt_proc with serde rename=<legacy> alias=<new> pins plus duplicate-key rejection; added PROMPT_PROC_ORIGIN (value pinned xprompt-proc) keeping XPROMPT_PROC_ORIGIN alias with // legacy xprompt spelling; registered prompt_proc_origin binding alongside xprompt_proc_origin; removed affected root re-exports and prelude aliases; applied permitted parity-test initializer change (prompt_proc: None). Tests: old/new request equality, duplicate rejection, byte-identical output, proc mutation/read paths. Residual xprompt hits: all added lines are serde pins/aliases, legacy-reader tests, or // legacy annotations; no new internal leftovers. Evidence: sase-core sase tool run check 75be3941d28d7bda46eddec155b946ad succeeded; primary just check monitor 4s7n3ptqkpqh / tool e37215f8b94269297abded6a0b1caf68 verdict no_new_failures (7 KNOWN with witnesses 03ee989318aabda9dc9e079e1c734367, 1b2d7636e7f0915c1edcb415fc0feb11).

[2026-10-02T13:56:51Z · sase-1eq.1.1.2--1] runtime-wire-names done: sase-core sase tool run check 75be3941d28d7bda46eddec155b946ad succeeded (fmt, features, clippy, workspace+PyO3/LSP/script tests); cargo fmt --check clean; epic-symbols empty. Primary just check monitor 4s7n3ptqkpqh verdict no_new_failures — 7 KNOWN failures with independent witnesses, none caused by this phase. Both prompt_proc_origin/xprompt_proc_origin bindings agree on legacy xprompt-proc value.

## Dependencies

- **Depends on:** [sase-1eq.1.1.1](sase-1eq.1.1.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.1.1.3](sase-1eq.1.1.3.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.1.2.md) | [sase-1eq.1.1.2](sase-1eq.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@421324b`](https://github.com/sase-org/sase-core/commit/421324bf2042cd7f7ffa8110b3027e8c0974a9ec) | feat(core-expand): rename runtime wires toward macros with pinned legacy output | [sase-1eq.1.1.2](sase-1eq.1.1.2.md) | 2026-10-02 09:58:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.1.1.2--1][1] | Need phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.1.2.md

<!-- sase:referenced-by:end -->

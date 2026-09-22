# Bead: sase-165.2 — sase-core agent guide, provider shims, module map, README

[Bead Pages](../README.md) / [sase-165](README.md) / sase-165.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0p2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0p2.md) · **Assignee:** `sase-165.2` · **Size:** medium
**Created:** 2026-09-22 08:18:22 EDT · **Closed:** 2026-09-22 11:13:51 EDT
**Plan:** [202609/sase\_core\_p0\_agent\_maintainability.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_p0_agent_maintainability.md)

## Description

core-agent-guide: rewrite sase-core AGENTS.md to the target content, add CLAUDE.md and GEMINI.md import shims, add `just modules` and fill the missing top-level `//!` summaries. Delete the stale sase_core_py binding manifest and cut the README down to current facts.

## Notes

[2026-09-22T15:13:14Z · sase-165.2] core-agent-guide done: AGENTS.md rewritten to 97 lines (cap 150); CLAUDE.md=@AGENTS.md and GEMINI.md=@./AGENTS.md shims added; just modules added (112 modules, zero empty summaries) with //! one-liners for the 15 missing modules; sase_core_py lib.rs manifest deleted (736 -> 88 lines), kept QueryErrorWire note plus dict-shapes prose with stale sase_100/ path and converter location fixed; README.md cut 309 -> 50 lines with all keeps and zero stale refs. Dry-run of add-a-binding recipe vs 45a966c: only extra edit sites were lib.rs manifest line + prelude core_ alias, exactly the retired sites. just check green (exit 0). Note: just fmt also reformatted 3 pre-existing hunks from 19ee7a0 (fleet_attention.rs, gateway fleet_attention test) that blocked the fmt gate.

[2026-09-22T15:13:51Z · sase-165.2] Verified: AGENTS.md 97 lines; just modules lists 112 modules with no empty summaries; just check exit 0 (fmt/clippy/tests/script-test); no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-165.1](sase-165.1.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-165.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.2/README.md) | [sase-165.2](sase-165.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@035851e`](https://github.com/sase-org/sase-core/commit/035851e0dad8a7ce00bf00735014e5d473c8786a) | docs(core): agent guide, provider shims, module map, README | [sase-165.2](sase-165.2.md) | 2026-09-22 11:15:24 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-165.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-165.2/README.md

<!-- sase:referenced-by:end -->

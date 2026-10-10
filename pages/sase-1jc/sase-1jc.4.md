# Bead: sase-1jc.4 — Stabilize macro aliases and strict input types

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.4` · **Size:** medium
**Created:** 2026-10-09 22:28:24 EDT · **Closed:** 2026-10-10 06:21:37 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

macro-contracts: Follow phase 4 and the shared removal checklist. Retire legacy_xprompt_syntax and strict_macro_input_types; close sase-1fj and sase-1g9. Preserve the On branch accepting xprompt aliases, legacy discovery and plugin names, while removing rollout rejection policy and unknown-type-to-line fallback. Make Rust config and LSP normalization follow the same unconditional semantics. Keep duplicate-name and malformed-input errors and durable readers.

## Notes

[2026-10-10T10:21:17Z · sase-1jc.4] PROPOSED FOLLOW-UP: 13 just-check failures reproduce identically on clean base b81673283a (verified via stash): test_default_config_matches_public_schema (agent_auto_restart spare_process_patterns), test_mutex_groups_found (21 vs 20), test_agents_help_renders_sorted_subcommands (missing auto-restart), test_tui_app_import budget 3518>3513, test_agents_live_profile vocab, test_finalizer_status trailing field, 2 marker-audit tests, 2 completion snapshot tests, pypi lock-path, bob digest, timezone guard; plus 2 flakes (monitor_capacity_e2e, detach watchdog) that pass on rerun

[2026-10-10T10:21:22Z · sase-1jc.4] PROPOSED FOLLOW-UP: macros.md memory note still describes typed Proc launches as beta/rollout; update to unconditional per retirement (skipped per epic macro_memory=no decision)

[2026-10-10T10:21:26Z · sase-1jc.4] PROPOSED FOLLOW-UP: tui_perf.md rule 14 still carries refresh-token flag condition; update to unconditional while preserving perf requirements (skipped per epic refresh_memory=no decision)

[2026-10-10T10:21:37Z · sase-1jc.4] Retired legacy_xprompt_syntax + strict_macro_input_types (closed sase-1fj, sase-1g9). Python: removed 2 registry members, schema regen (19 flags remain), deleted flag helper/env/init-option transport and all Off branches; aliases + collision errors + durable readers kept. sase-core: macro_syntax/catalog/LSP normalization unconditional (old wire fields accepted-and-ignored); strict resolve already unconditional. Verified: sase-core gate GREEN; primary just check lint gates green + 54546 passed; 13 failures reproduce identically on clean base (recorded as follow-up), 2 flakes pass on rerun. Terminology guards green.

## Dependencies

- **Depends on:** [sase-1jc.3](sase-1jc.3.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.5](sase-1jc.5.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.4/README.md) | [sase-1jc.4](sase-1jc.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e3b0907`](https://github.com/sase-org/sase-core/commit/e3b0907b8d3eafcd3d673b5af0c071d6a9f8370c) | feat(macros): retire legacy-xprompt opt-out; unconditional alias acceptance | [sase-1jc.4](sase-1jc.4.md) | 2026-10-10 06:23:12 EDT |
| sase | [`8a2f344`](https://github.com/sase-org/sase/commit/8a2f344626143a97b29d63d202d3537ac7860587) | feat(flags): retire legacy\_xprompt\_syntax and strict\_macro\_input\_types; macro aliases and strict input types unconditional | [sase-1jc.4](sase-1jc.4.md) | 2026-10-10 06:27:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jc.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.4/README.md

<!-- sase:referenced-by:end -->

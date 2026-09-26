# Bead: sase-1ao.3.1 — Make adjacent directive cleanup disjoint and verify both frontends

[Bead Pages](../README.md) / [sase-1ao.3](sase-1ao.3.md) / sase-1ao.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1ao.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ao.land.md) · **Assignee:** `sase-1ao.3.1` · **Size:** medium
**Created:** 2026-09-26 13:15:21 EDT · **Closed:** 2026-09-26 14:30:00 EDT
**Plan:** [202609/model\_shortcut\_adjacent\_directives.md](https://github.com/sase-org/sase--plans/blob/main/202609/model_shortcut_adjacent_directives.md)

## Description

adjacent_cleanup: repair the shared Rust edit planner, pin its commit in sase, and add ACE/LSP applied-document regression coverage.

## Notes

[2026-09-26T18:01:49Z · sase-1ao.3.1] PROPOSED FOLLOW-UP: sase-core `sase tool run check` fails at clippy with 7 pre-existing errors (clippy::nonminimal_bool x5, clippy::manual_range_contains x2 on stable 1.95.0) in agent_runtime.rs, maintenance.rs, fleet_owner_facts.rs, provider_usage/mod.rs, receipt.rs, triage.rs; identical on clean base e654e7c, no existing task bead found

[2026-09-26T18:29:32Z · sase-1ao.3.1--1] PROPOSED FOLLOW-UP: sase just check fails at lint (feature flags) with rule 7 closed flag bead sase-1ad (Retire card_blocks) still has a surviving card_blocks definition and rule 8 live flag bead sase-1ar (Retire legacy_sase_shell_syntax, created ~2h ago by bbugyi200.athena.sase-1ab.3) has no definition yet; both owned by other lanes, none of my files (sase-core-revision.txt plus 4 model-shortcut test files) touch flag definitions; identical failure independent of this phase diff. Also: the clippy follow-up in note #1 matches existing task bead sase-1an (sase-core clippy denies manual_range_contains and nonminimal_bool).

[2026-09-26T18:30:00Z · sase-1ao.3.1--1] adjacent_cleanup: core 041f53b shrinks shared padding so =alias/==model accept removes every adjacent directive with disjoint edits; pin at 041f53b; ACE/LSP parity plus widget accept/undo green; sase just test-scoped 905 passed; focused 146 passed; sase-core check blocked only by 7 pre-existing clippy lints identical on base; just check gate blocked only by unrelated lint-flags rule7/rule8 owned by sase-1ad/sase-1ar lanes (PROPOSED FOLLOW-UP noted)

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ao.3.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ao.3.1.md) | [sase-1ao.3.1](sase-1ao.3.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@041f53b`](https://github.com/sase-org/sase-core/commit/041f53b88c9acd0fe86afdb8649ea910cb25d2ed) | fix(core): remove adjacent model directives with disjoint edits | [sase-1ao.3.1](sase-1ao.3.1.md) | 2026-09-26 13:30:37 EDT |
| sase | [`1a38e71`](https://github.com/sase-org/sase/commit/1a38e711d2d60466cb6a7b560d1193ae498aec49) | test(adjacent-cleanup): disjoint accept coverage for =alias/==model shortcuts (sase-1ao.3.1 already closed) | [sase-1ao.3.1](sase-1ao.3.1.md) | 2026-09-26 14:38:52 EDT |

# Bead: sase-1jc.5 — Stabilize agent-session and turn compatibility aliases

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.5` · **Size:** medium
**Created:** 2026-10-09 22:28:25 EDT · **Closed:** 2026-10-10 07:30:16 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

identity-aliases: Follow phase 5 and the shared removal checklist. Retire legacy_agent_family_syntax and legacy_sase_shell_syntax; close sase-18l and sase-1ar. Keep all currently enabled alias normalization, including Rust's family keyword alias, and delete the flag-off rejection branches. Preserve canonical output, conflict validation, and old durable records. Do not interpret legacy flag names as permission to remove their enabled compatibility behavior.

## Notes

[2026-10-10T10:51:01Z · sase-1jc.5] PROPOSED FOLLOW-UP: Update macros.md memory note to describe retired agent-family/shell aliases as unconditional (epic decision macro_memory=no skipped it)

[2026-10-10T10:51:06Z · sase-1jc.5] PROPOSED FOLLOW-UP: Update tui_perf.md memory note if it describes refresh tokens as flag-gated (epic decision refresh_memory=no skipped it; no refresh-token change in this phase)

[2026-10-10T11:30:07Z · sase-1jc.5] PROPOSED FOLLOW-UP: 17 just-check failures reproduce identically on clean base 8a2f344626 (same pre-existing set triaged by sase-1jc.4: config_schema, completion build/snapshot x3, parser help, query-profile vocab, timezone guard, file-hook bob, pypi flow, import budget, autonomy gates x2, marker audits x2, bindings tool, agent-scan wire) plus 1 flake (fakey monitor-capacity e2e, passes alone in 65s)

[2026-10-10T11:30:16Z · sase-1jc.5] Retired legacy_agent_family_syntax + legacy_sase_shell_syntax: removed both enum/registry definitions, regenerated sase.schema.json, made family/session and shell/turn alias normalization unconditional (conflict errors, canonical output, durable readers kept; Rust hidden family alias preserved per plan; no sase-core change so no revision-pin update). Docs (configuration/agent_sessions/notifications) now describe accepted aliases; tests converted to unconditional regressions; dead guard allowlist entries pruned. Closed sase-18l and sase-1ar. Verified: fmt/ruff/mypy green; 81 focused tests green; just check 54539 passed with 17 failures reproducing identically on clean base 8a2f344626 (recorded as PROPOSED FOLLOW-UP) + 1 flake passing alone. No epic-symbols.

## Dependencies

- **Depends on:** [sase-1jc.4](sase-1jc.4.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.6](sase-1jc.6.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.5/README.md) | [sase-1jc.5](sase-1jc.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f5070d`](https://github.com/sase-org/sase/commit/2f5070d1291c8110b4d9b910cf353d1a47e4b2de) | feat(flags): retire legacy\_agent\_family\_syntax and legacy\_sase\_shell\_syntax; agent-session and turn aliases unconditional | [sase-1jc.5](sase-1jc.5.md) | 2026-10-10 07:32:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jc.5][1] | Need phase scope notes and history | 2 |
| read-by | [agent:sase-1jm.1][2] | Confirm the active owner for closed flag definitions reported by just check | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.1/README.md

<!-- sase:referenced-by:end -->

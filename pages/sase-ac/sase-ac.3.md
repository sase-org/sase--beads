# Bead: sase-ac.3 — Resolve registry-backed project xprompts independent of cwd

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.3` · **Size:** medium
**Created:** 2026-07-28 11:41:35 UTC · **Closed:** 2026-07-28 12:48:57 UTC
**Plan:** [202607/xprompt\_project\_identity.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_project_identity.md)

## Description

resolver: teach the xprompt loader to read a registered project's checkout xprompts through the project registry so `#sase/reads` expands even when the process cwd is not that checkout.

## Notes

[2026-07-28T12:48:44Z · sase-ac.3] Implemented registry-backed project xprompt resolution outside cwd with canonical namespace selection, current-checkout precedence, enabled-project filtering, and direct namespaced-reference expansion. Added regressions for outside-workspace loading/expansion, alternate-checkout precedence, and disabled projects. Verification: just lint passed; just test passed (22,904 passed, 7 skipped); focused resolver/compatibility tests passed (89 passed). just check passed formatting and all lint stages but its SASE plan-link validation is blocked by 229 unrelated pre-existing sidecar artifact-link errors.

## Dependencies

- **Depends on:** [sase-ac.1](sase-ac.1.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.3/README.md) | [sase-ac.3](sase-ac.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`9148e45`](https://github.com/sase-org/sase/commit/9148e45e1829a445e772a07c8c71b6d919a6ff56) | feat(xprompt): resolve registered project prompts outside cwd (sase-ac.3) | [sase-ac.3](sase-ac.3.md) | 2026-07-28 12:50:28 |

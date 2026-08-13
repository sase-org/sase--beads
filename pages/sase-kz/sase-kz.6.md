# Bead: sase-kz.6 — Nest-vs-reset policy for every non-trigger expansion caller

[Bead Pages](../README.md) / [sase-kz](README.md) / sase-kz.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zm.md) · **Assignee:** `sase-kz.6` · **Size:** small
**Created:** 2026-08-13 12:28:57 EDT · **Closed:** 2026-08-13 15:33:06 EDT
**Plan:** [plans:202608/nested\_snippet\_sessions.md](https://github.com/sase-org/sase--plans/blob/main/202608/nested_snippet_sessions.md)

## Description

call_sites: make each of the five non-trigger callers of the expansion entry point declare whether it nests inside the active session or replaces it, and cover the whole-pane skeleton reset.

## Notes

[2026-08-13T19:33:06Z · sase-kz.6] Implemented explicit snippet expansion session policy for all five non-trigger callers: file completion, soft completion, Ctrl+T xprompt skeleton, named-arg skeleton all pass session_policy=nest, and whole-pane local xprompt replacement passes session_policy=reset. Added call-site regression coverage and cleaned stale Symvision closed-bead exemptions by privatizing facade internals and using live clear/retreat consumers. Verified with just install, focused pytest coverage for snippet call sites/facade/prompt snippet paths, just _lint-symvision, and just check (scoped lane escalated to full suite and passed).

[2026-08-13T19:34:06Z · sase-kz.6] Verified explicit snippet expansion session policies, whole-pane reset behavior, focused pytest coverage, Symvision, and just check.

## Dependencies

- **Depends on:** [sase-kz.5](sase-kz.5.md) ✓ · ⧖ 2026-08-13
- **Blocks:** [sase-kz.8](sase-kz.8.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kz.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kz.6/README.md) | [sase-kz.6](sase-kz.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`53c87b7`](https://github.com/sase-org/sase/commit/53c87b7585ed872e05ee125b74b65bf71dd6270e) | fix: make snippet expansion session policy explicit | [sase-kz.6](sase-kz.6.md) | 2026-08-13 15:35:37 EDT |

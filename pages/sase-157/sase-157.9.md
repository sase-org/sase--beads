# Bead: sase-157.9 — Make the macOS leg required and document the loop

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.9` · **Size:** small
**Created:** 2026-09-21 06:25:54 EDT · **Closed:** 2026-09-21 12:02:29 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

macos-ci-required: drop the advisory escape hatch so the macOS leg blocks, and document the macOS verification loop and the platform-path rule for future contributors.

## Notes

[2026-09-21T16:01:29Z · sase-157.9] PROPOSED FOLLOW-UP: sudo_runner parallel-load flakes — post_spawn_identity_failure_reaps_barred_worker (ParseIntError Empty unwrap) and cwd_removed_after_authentication_fails_before_dispatch_and_cleans_up (!cwd.exists) each failed once across repeated Linux just check runs and passed on rerun; consider stabilizing or quarantining

[2026-09-21T16:02:29Z · sase-157.9] macOS leg required (continue-on-error removed, YAML valid); AGENTS.md carries platform-path rule + macOS loop; README verification goes through check.sh; full mac suite green (3198 lib tests, 0 failed) on final tree; Linux just check RC=0 on final tree; fixed git_object_sharing expectation to canonicalize per shared rule

## Dependencies

- **Depends on:** [sase-157.5](sase-157.5.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-157.6](sase-157.6.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-157.7](sase-157.7.md) ✓ · ⧖ 2026-09-21
- **Depends on:** [sase-157.8](sase-157.8.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.9/README.md) | [sase-157.9](sase-157.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d99ba11`](https://github.com/sase-org/sase-core/commit/d99ba118f8108cfd347a63b12db055470ae69b2d) | fix(sase-core): make macOS CI leg blocking and fix canonicalization test | [sase-157.9](sase-157.9.md) | 2026-09-21 12:04:38 EDT |

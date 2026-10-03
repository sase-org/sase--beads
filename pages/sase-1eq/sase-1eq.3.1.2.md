# Bead: sase-1eq.3.1.2 — Package and module paths

[Bead Pages](../README.md) / [sase-1eq.3.1](sase-1eq.3.1.md) / sase-1eq.3.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.md) · **Assignee:** `sase-1eq.3.1.2` · **Size:** medium
**Created:** 2026-10-02 19:30:26 EDT · **Closed:** 2026-10-03 00:09:56 EDT
**Plan:** [202610/sase\_modules\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md)

## Description

paths: Move non-TUI xprompt packages and modules onto macro paths, retarget imports and package resource paths, and add the temporary import shim.

## Notes

[2026-10-03T04:09:37Z · sase-1eq.3.1.2] PROPOSED FOLLOW-UP: just check _lint-flags fails on rule 7 (closed flag bead sase-1ey still defines three_pane_splits); reproduces identically on clean base via just _lint-flags, unrelated to the paths rename

[2026-10-03T04:09:56Z · sase-1eq.3.1.2] Moved sase/xprompt to sase/macro, sase/xprompts to sase/macros, default_xprompts to default_macros, tests/xprompt to tests/macro, and 123 further xprompt paths to macro names via git mv; retargeted all in-repo imports, mock/importlib module strings, and package resource paths (loader skills/sources, catalog prompts, LSP env, stitch audit, init-skills guard); TUI diffs limited to import module paths, module-attr usages, doc refs, and mock strings. Added temp sase.xprompt shim (synthetic submodules + lazy swarm finder, all 22 names resolve, mock.patch isolation verified) with agent registration line. Verified: sase tool run check passes fmt/ruff/mypy/model-policy/keep-sorted with sole _lint-flags failure reproduced identically on clean base (recorded as follow-up); full pytest collection clean (51870 tests); 393 targeted tests pass; 4 shim proof imports pass in fresh interpreters

## Dependencies

- **Depends on:** [sase-1eq.3.1.1](sase-1eq.3.1.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.3.1.3](sase-1eq.3.1.3.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.3.1.2/README.md) | [sase-1eq.3.1.2](sase-1eq.3.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`117f577`](https://github.com/sase-org/sase/commit/117f5779d32622cc51bef674030cea49c52a8db9) | refactor(sase-modules): move non-TUI xprompt packages onto macro paths (sase-1eq.3.1.2) | [sase-1eq.3.1.2](sase-1eq.3.1.2.md) | 2026-10-03 00:20:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.3.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.3.1.2/README.md

<!-- sase:referenced-by:end -->

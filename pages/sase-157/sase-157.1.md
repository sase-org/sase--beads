# Bead: sase-157.1 — Fix the managed-tmp reap guard and disarm its test

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.1` · **Size:** small
**Created:** 2026-09-21 06:25:43 EDT · **Closed:** 2026-09-21 06:41:54 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

reap-guard: canonicalize the unsafe-root denylist so the guard fires on macOS, widen it to the platform temp aliases and $TMPDIR/$HOME, and rewrite the guard test so it can never apply a removal.

## Notes

[2026-09-21T10:41:54Z · sase-157.1] reap-guard done: validate_reap_root now compares canonically on both sides (shared-rule branch: production canonicalizes, so every denylist entry is stored raw+canonicalized via push_denied); denylist widened to /,/tmp,/var/tmp,/private/tmp,/private/var/tmp plus TMPDIR and HOME; cwd guard unchanged; guard test is table-driven over all denied roots with apply:false so a regression cannot reap. Verified: just check green on Linux; full sase_core --lib on mac (no skip) has broad_cleanup_roots_are_rejected passing with /private/tmp untouched, 4 remaining failures are pre-existing unrelated clusters (agent_artifact_run_retention, bead cli x2, git_object_sharing) owned by later phases; mac checkout restored clean. Caller check: sase default root ~/.sase/tmp is unaffected; SASE_TMPDIR pointed at TMPDIR/HOME is now refused (intended). Left request() helper default apply:true since all other callers use tempdir roots and need live apply.

## Dependencies

- **Blocks:** [sase-157.2](sase-157.2.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.1/README.md) | [sase-157.1](sase-157.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@60782f2`](https://github.com/sase-org/sase-core/commit/60782f2dfc2c82ceeb59394d8ac46d8a096317c0) | fix(sase-core): harden managed\_tmp reap-root guard and disarm guard test | [sase-157.1](sase-157.1.md) | 2026-09-21 06:45:45 EDT |

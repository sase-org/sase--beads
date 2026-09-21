# Bead: sase-157.7 — Reconcile canonicalized paths across sase\_core and the bindings

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.7` · **Size:** medium
**Created:** 2026-09-21 06:25:51 EDT · **Closed:** 2026-09-21 09:01:35 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

core-path-expectations: fix the five remaining sase_core and sase_core_py failures caused by comparing canonicalized paths against caller-supplied ones, deciding per site whether production or the expectation is wrong.

## Notes

[2026-09-21T13:01:35Z · sase-157.7] All 5 core-path-expectations sites fixed as production bugs (canonicalize both sides): bead design relativization, git alternates resolution, retention symlink walk, file-ref echo. 4 new symlinked-path regression tests failed pre-fix and pass post-fix; full ./scripts/check.sh all green on Linux (fmt, clippy -D warnings, workspace tests incl. sase_core_py bindings, 56 script-tests). macOS proof left to advisory CI leg.

## Dependencies

- **Depends on:** [sase-157.3](sase-157.3.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.9](sase-157.9.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.7/README.md) | [sase-157.7](sase-157.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2b78764`](https://github.com/sase-org/sase-core/commit/2b7876444f58d6098e81f5b2e8991b186f1126fe) | fix(sase-core): reconcile canonicalized paths across sase\_core and bindings | [sase-157.7](sase-157.7.md) | 2026-09-21 09:02:36 EDT |

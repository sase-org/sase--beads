# Bead: sase-ae.1 — Source-integrity guard for skill deploys

[Bead Pages](../README.md) / [sase-ae](README.md) / sase-ae.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ae.1` · **Size:** medium
**Created:** 2026-07-28 11:54:03 UTC · **Closed:** 2026-07-28 12:21:32 UTC
**Plan:** [202607/skill\_deploy\_thrash.md](https://github.com/sase-org/sase--plans/blob/main/202607/skill_deploy_thrash.md)

## Description

guard: refuse a chezmoi skill deploy when the invoking workspace has uncommitted xprompt template edits or a HEAD that is not an ancestor of the canonical branch, add an --allow-dirty escape hatch, and leave read-only and non-chezmoi paths untouched.

## Notes

[2026-07-28T12:21:06Z · sase-ae.1] Implemented the chezmoi skill source-integrity preflight and -D/--allow-dirty escape hatch. Dirty xprompt paths and HEAD commits absent from the canonical branch are reported before writes; --check, --diff, --dry-run, non-chezmoi, and no-change paths remain read-only/unaffected. Verification: focused suite 60 passed; just check passed fmt, markdown fmt, keep-sorted, ruff, mypy, pyscripts, symvision, and toobig, then stopped on 229 pre-existing plans-sidecar link errors; standalone full just test passed 22,902 tests with 7 skipped.

## Dependencies

- **Blocks:** [sase-ae.2](sase-ae.2.md) ✓
- **Blocks:** [sase-ae.5](sase-ae.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ae.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ae.1/README.md) | [sase-ae.1](sase-ae.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3537aa1`](https://github.com/sase-org/sase/commit/3537aa141d844123c02fbca3552dbcc669673b3d) | feat(skills): guard chezmoi deploy source integrity (sase-ae.1) | [sase-ae.1](sase-ae.1.md) | 2026-07-28 12:24:10 |

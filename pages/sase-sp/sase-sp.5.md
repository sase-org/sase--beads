# Bead: sase-sp.5 — Publish the commit consent model where agents actually read it

[Bead Pages](../README.md) / [sase-sp](README.md) / sase-sp.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.5` · **Size:** medium
**Created:** 2026-08-24 09:19:10 EDT · **Closed:** 2026-08-24 12:38:55 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Description

consent: carry the commit-by-default rule and per-repository provenance evidence in `sase final context` output, rewrite the `/sase_final` skill around authoring, and remove the self-contradiction in the declaration-recovery prompt.

## Notes

[2026-08-24T16:38:16Z · sase-sp.5] PROPOSED FOLLOW-UP: Add the commit-by-default consent rule to protected SASE memory - requires explicit user permission to edit src/sase/main/init_memory/templates/memory-sase.template.md and then run sase memory init.

[2026-08-24T16:38:55Z · sase-sp.5] Implemented model-visible commit_declaration guidance/evidence, updated recovery prompt and /sase_final source, and removed stale closed-bead Symvision entries. Verified: just install; just fmt; focused pytest for finalizer declaration/recovery and skill source; sase skill init --diff; just _lint-symvision; git diff --check; sase bead epic-symbols sase-sp.5 reported no entries. just check passed fmt, keep-sorted, ruff, mypy, feature-flags, pyscripts, test-waits, changelog, terminology, symvision, and toobig; it is blocked only by existing init memory --check drift.

## Dependencies

- **Depends on:** [sase-sp.3](sase-sp.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sp.6](sase-sp.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.5/README.md) | [sase-sp.5](sase-sp.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4580649`](https://github.com/sase-org/sase/commit/45806495fa3905e8d279f1bc504a24a9f02461e2) | feat(final): publish commit declaration consent model | [sase-sp.5](sase-sp.5.md) | 2026-08-24 12:50:15 EDT |

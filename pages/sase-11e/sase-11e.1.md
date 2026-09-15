# Bead: sase-11e.1 — Shared configuration names and compatibility contract

[Bead Pages](../README.md) / [sase-11e](README.md) / sase-11e.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l8.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l8.r0.md) · **Assignee:** `sase-11e.1` · **Size:** medium
**Created:** 2026-09-15 15:18:41 EDT · **Closed:** 2026-09-15 17:20:24 EDT
**Plan:** [202609/axe\_routines\_jobs.md](https://github.com/sase-org/sase--plans/blob/main/202609/axe_routines_jobs.md)

## Previously Closed

> ↺ Closed 2026-09-15T19:31:42Z · canceled
>
> forced by sase-11e: Decided to go with the name Batch instead of Routine.
>
> Reopened 2026-09-15T19:41:04Z by a status update

## Description

config_contract: implement Rust-owned public configuration name translation, exact source provenance, and the contract rollout flag.

## Notes

[2026-09-15T19:41:13Z · bryanbugyi34@gmail.com] I changed my mind on this. Routine still works better since it implies recurrence.

[2026-09-15T21:20:24Z · sase-11e.1] Verified: core just check with uv Python LD_LIBRARY_PATH, main just check with uv Python LD_LIBRARY_PATH, focused AXE tests, feature-flag schema/check_feature_flags, and epic-symbols clean.

## Dependencies

- **Blocks:** [sase-11e.2](sase-11e.2.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11e.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11e.1/README.md) | [sase-11e.1](sase-11e.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e41f651`](https://github.com/sase-org/sase/commit/e41f651eb9fd6479d105c618d24e0a89db972991) | feat(axe): add routine/job config contract | [sase-11e.1](sase-11e.1.md) | 2026-09-15 17:22:53 EDT |
| sase-core | [`sase-core@a68ee7d`](https://github.com/sase-org/sase-core/commit/a68ee7ddaccad67330e9d1561ff9a64fab1d0990) | feat(axe): normalize routine/job config names | [sase-11e.1](sase-11e.1.md) | 2026-09-15 17:25:36 EDT |

# Bead: sase-11l.11.3 — Persist capture summaries and report expiry releases

[Bead Pages](../README.md) / [sase-11l.11](sase-11l.11.md) / sase-11l.11.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.land.md) · **Assignee:** `sase-11l.11.3` · **Size:** medium
**Created:** 2026-09-18 18:08:43 EDT · **Closed:** 2026-09-19 02:16:43 EDT
**Plan:** [202609/hold\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_landing_repairs.md)

## Description

capture-lifecycle: retain effective arm-time counts across rebind, render them in CLI and Holds pane, and carry validated expiry and liveness prune outcomes to deduplicated notifications.

## Notes

[2026-09-19T06:16:43Z · sase-11l.11.3--1] Verified capture-lifecycle: optional typed arm-time capture summary is persisted on the Rust hold record and preserved across rebind; legacy records without capture render as capture not recorded rather than invented zeros; capture counts use effective identities after scope and armer/kin exclusion (pending still skips undispatched procs); CLI hold list/show/JSON and the Holds pane render the stored arm-time summary; locked Rust prune returns validated expiry vs dead-armer outcomes plus an agent_holds.prune.json sidecar so later mutations cannot swallow evidence until a list drains it; Python lifecycle adapter notifies once (deduped by armer key), including the exact TTL boundary; malformed stores fail open without bogus notifications or blocking admission. sase-core just check and SASE just check both passed (monitor td9p42yzfgs6, exit 0). Pin bump of sase-core-revision.txt is deferred until the unpublished sase-core commit is released (local just rust-dev-install was used).

## Dependencies

- **Depends on:** [sase-11l.11.2](sase-11l.11.2.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-11l.11.4](sase-11l.11.4.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.11.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.11.3.md) | [sase-11l.11.3](sase-11l.11.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a1bb1df`](https://github.com/sase-org/sase/commit/a1bb1df4544d68bf28168d448aab94b708ea0b17) | feat(hold): render arm-time capture summaries and expiry releases | [sase-11l.11.3](sase-11l.11.3.md) | 2026-09-19 02:22:18 EDT |
| sase-core | [`sase-core@6fe31cb`](https://github.com/sase-org/sase-core/commit/6fe31cb076d067e2a61252c4f05ce27a888b3b0a) | feat(hold): persist capture summaries and return prune evidence | [sase-11l.11.3](sase-11l.11.3.md) | 2026-09-19 02:25:36 EDT |

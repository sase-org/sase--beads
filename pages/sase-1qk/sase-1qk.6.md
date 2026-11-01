# Bead: sase-1qk.6 — Bound the shared pending-action store

[Bead Pages](../README.md) / [sase-1qk](README.md) / sase-1qk.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.16r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.16r.md) · **Assignee:** `sase-1qk.6` · **Size:** medium
**Created:** 2026-11-01 12:02:56 EST · **Closed:** 2026-11-01 15:37:35 EST
**Plan:** [202611/16p\_stall\_handoff\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/16p_stall_handoff_recovery.md)

## Description

pending-action-prune: prune old already-handled entries in sase-core's pending-action store without reviving handled notifications.

## Notes

[2026-11-01T19:29:23Z · sase-1qk.6] PROPOSED FOLLOW-UP: Raise/publish the sase-core-rs floor to cover existing linked-core capabilities; the unchanged SASE check reported blocked_unpublished for 0.43.2 (15 capabilities from prior commits, none added by this phase). Related floor-gated fallback retirement: sase-1iy.

[2026-11-01T20:37:35Z · sase-1qk.6--2] Confirmed seven-day handled-action pruning and non-revival regression coverage in sase-core and sase; sase tool run check d19edc7d9c37490b46e6e9367b4ca0b3 exited 0 with pass triage, and epic-symbols reported none.

## Dependencies

- **Depends on:** [sase-1qk.1](sase-1qk.1.md) ✓ · ⧖ 2026-11-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qk.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qk.6.md) | [sase-1qk.6](sase-1qk.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6d33166`](https://github.com/sase-org/sase-core/commit/6d3316690815b5a8281ff7081383dae411ec11f8) | feat(notifications): prune handled pending actions after one week | [sase-1qk.6](sase-1qk.6.md) | 2026-11-01 15:38:27 EST |
| sase | [`c5fdcd1`](https://github.com/sase-org/sase/commit/c5fdcd10cd8a6c678b8a806a1cdad4cefc3b3595) | test(pending-actions): use integral timestamps in transport round-trip | [sase-1qk.6](sase-1qk.6.md) | 2026-11-01 15:39:54 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qk.6--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qk.6.md

<!-- sase:referenced-by:end -->

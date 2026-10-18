# Bead: sase-1lh.7.5.4.3.3.4.4.2 — Pin the committed portable core and verify the consumer

[Bead Pages](../README.md) / [sase-1lh.7.5.4.3.3.4.4](sase-1lh.7.5.4.3.3.4.4.md) / sase-1lh.7.5.4.3.3.4.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.land.md) · **Assignee:** `sase-1lh.7.5.4.3.3.4.4.2` · **Size:** small
**Created:** 2026-10-17 21:56:54 EDT · **Closed:** 2026-10-17 22:51:18 EDT
**Plan:** [202610/finish\_portable\_core\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_portable_core_release.md)

## Description

pin: ratchet the sase core pin past the completed portability fix and verify compatibility.

## Notes

[2026-10-18T02:51:18Z · sase-1lh.7.5.4.3.3.4.4.2] Verified core 72bf9203758d (openat c_uint promotion) is on sase-core origin/master; ratcheted sase-core-revision.txt dd56b94a -> 72bf9203758d via just ratchet-core-revision (exit 2 = applied). Intervening core diff is only mobile_pairing/fs.rs (no binding/wire changes). just fix clean; sase tool run check 4be2e7f8e57c29b2db0f2c7e2eb1640a succeeded/exit 0 (includes binding checks). No epic symbols. Did not run check-full or touch dependency window/release metadata. Pin commit is host-created at finalize; watch phase must verify macOS CI.

## Dependencies

- **Depends on:** [sase-1lh.7.5.4.3.3.4.4.1](sase-1lh.7.5.4.3.3.4.4.1.md) ✓ · ⧖ 2026-10-17
- **Blocks:** [sase-1lh.7.5.4.3.3.4.4.3](sase-1lh.7.5.4.3.3.4.4.3.md) ◐ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.4.3.3.4.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lh.7.5.4.3.3.4.4.2/README.md) | [sase-1lh.7.5.4.3.3.4.4.2](sase-1lh.7.5.4.3.3.4.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae9f044`](https://github.com/sase-org/sase/commit/ae9f044bb39c22ab5702031b1507249e29a2d4da) | chore(core): pin sase-core past the portable openat fix | [sase-1lh.7.5.4.3.3.4.4.2](sase-1lh.7.5.4.3.3.4.4.2.md) | 2026-10-17 22:51:59 EDT |

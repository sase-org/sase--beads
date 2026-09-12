# Bead: sase-zn.6 — Extend scratch hygiene to agent-created build directories and disk pressure

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.6` · **Size:** medium
**Created:** 2026-09-11 12:20:22 EDT · **Closed:** 2026-09-12 11:03:31 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

tmp-hygiene: give agent-created cargo/build scratch a managed home the reaper can actually see, and add size-aware pressure reaping so a multi-gigabyte directory is not held for a purely time-based horizon.

## Notes

[2026-09-12T15:03:31Z · sase-zn.6] Implemented managed per-agent TMPDIR/TMP/TEMP and CARGO_TARGET_DIR defaults, added managed agent-tmp/cargo-targets horizons plus size-pressure reaping for aged large build scratch and top-level residue, and updated chop/docs coverage. Verified with targeted pytest for reaper/env/chop contract and just check passing; sase bead epic-symbols sase-zn.6 reported no entries.

## Dependencies

- **Depends on:** [sase-zn.1](sase-zn.1.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.8](sase-zn.8.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.6/README.md) | [sase-zn.6](sase-zn.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2614668`](https://github.com/sase-org/sase/commit/2614668f48e89a61ee5c44dd380fd2707542f67a) | feat(tmp): route agent build scratch through managed reaper | [sase-zn.6](sase-zn.6.md) | 2026-09-12 11:05:07 EDT |

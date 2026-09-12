# Bead: sase-zn.1 — Reclaim athena now and move SASE\_TMPDIR off tmpfs and out of Syncthing

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.1` · **Size:** small
**Created:** 2026-09-11 12:20:19 EDT · **Closed:** 2026-09-11 15:56:05 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

host-relief: reclaim the two 31 GB scratch piles on athena, relocate SASE_TMPDIR out of the Syncthing-synced tree, and capture a documented before/after responsiveness baseline the later phases measure against.

## Notes

[2026-09-11T19:56:05Z · sase-zn.1] Verified on athena: SASE_TMPDIR moved from /home/bryan/tmp/sase to /home/bryan/.cache/sase/tmp in chezmoi-managed .profile and live ACE PID 2351038; removed 37G of SASE-named cargo/core/recovery scratch plus stale tui_trace.jsonl; /tmp dropped 20G->5.6G used, / free space 29G->51G, swap 30.4G->13.1G, ACE RSS/swap 10036968kB/3332948kB->766372kB/0kB; profiles captured under ~/.sase/perf/athena-host-relief-{before,after}-20260911T*.svg; docs/perf_runbook.md records the baseline. prettier --check docs/perf_runbook.md passed; just check was attempted but blocked on shared cargo build lock during stale sase_core_rs rebuild and interrupted cleanly.

## Dependencies

- **Blocks:** [sase-zn.6](sase-zn.6.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.7](sase-zn.7.md) ✓ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.1/README.md) | [sase-zn.1](sase-zn.1.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`32879ff`](https://github.com/sase-org/sase/commit/32879ff7f2416f123a86e2547ab2da1653edee61) | feat: Reclaim athena now and move SASE\_TMPDIR off tmpfs and out of Syncthing (sase-zn.1) | [sase-zn.1](sase-zn.1.md) | 2026-09-12 05:27:24 EDT |

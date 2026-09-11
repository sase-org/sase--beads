# Bead: sase-zn.5 — Narrow the artifact-index lock and stop authoritative syncs bypassing the signature check

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.03` · **Assignee:** `sase-zn.5` · **Size:** medium
**Created:** 2026-09-11 12:20:22 EDT
**Plan:** [202609/ace\_typing\_lag\_athena.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_typing_lag_athena.md)

## Description

index-tui-cadence: keep interactive index reads off the long maintenance lock and let authoritative dismissed-projection syncs short-circuit on an unchanged signature the same way non-authoritative ones already do.

## Dependencies

- **Depends on:** [sase-zn.2](sase-zn.2.md) ✓ · ⧖ 2026-09-11
- **Blocks:** [sase-zn.8](sase-zn.8.md) ◐ · ⧖ 2026-09-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.5/README.md) | [sase-zn.5](sase-zn.5.md) | 0 |

# Bead: sase-zs.1 — Borrow local objects when materializing sidecar SDD clones

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.1` · **Size:** small
**Created:** 2026-09-12 09:44:49 EDT · **Closed:** 2026-09-12 10:23:50 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

ref-reuse: pass a validated `reference_repo` down the sidecar-kind clone path so workspace materialization of the plans store stops re-downloading the full pack from GitHub on every launch.

## Notes

[2026-09-12T14:23:50Z · sase-zs.1] Implemented sidecar-kind reference reuse for primary local clones; verified no epic-symbol leftovers, focused SDD clone tests passed, and just check passed after full-suite escalation.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.1/README.md) | [sase-zs.1](sase-zs.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63653c5`](https://github.com/sase-org/sase/commit/63653c5ee1593d8deef0aa6890639af8f79ccfdb) | fix(sdd): reuse primary sidecar clone references | [sase-zs.1](sase-zs.1.md) | 2026-09-12 10:25:10 EDT |

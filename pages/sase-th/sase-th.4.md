# Bead: sase-th.4 — Rebaseline the stale ACE PNG goldens

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.4` · **Size:** medium
**Created:** 2026-08-25 07:32:01 EDT · **Closed:** 2026-08-25 08:07:39 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

visual: attribute every PNG mismatch to the landed UI change that caused it, then regenerate the stale goldens and settle the two marginal nodes that flicker between runs.

## Notes

[2026-08-25T12:07:39Z · sase-th.4] Verified visual rebaseline: accepted 28 attributed stale ACE PNG goldens, fixed slow-tools/procs visual wait races, and final strict just test-visual passed 786/786 with 1 skipped. just check was run after formatting the current HEAD drift in src/sase/sdd/_store_link.py; it reaches the known sibling symvision failures for the dead glossary/memory-web symbols owned by another phase.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-th.4/README.md) | [sase-th.4](sase-th.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`442d1d4`](https://github.com/sase-org/sase/commit/442d1d4e733f7095a51b1cbc7187cfe23c156abf) | test(ace): rebaseline stale visual goldens | [sase-th.4](sase-th.4.md) | 2026-08-25 08:09:05 EDT |

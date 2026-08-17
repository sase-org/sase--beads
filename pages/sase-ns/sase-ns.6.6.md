# Bead: sase-ns.6.6 — Task backlog top five — turn the mandatory verification gates green

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.land`
**Created:** 2026-08-17 04:03:10 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

`just check-full`'s last gate (`just selection-health --fail-on-new-flake`) stops reporting nodes that were already fixed, and stops reporting the two live full-parallel-lane flakes it currently names; the recurring generated-memory drift that flips `just check` red at the SASE validation step can no longer reappear undetected; and monitor reconciliation's locked settle path stops issuing an archive-scaled artifact-index query per candidate. Closes task beads sase-o0, sase-nd, sase-nz, sase-n0, and sase-ne.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.land/README.md) | [sase-ns.6.6](sase-ns.6.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf7eeee`](https://github.com/sase-org/sase/commit/cf7eeee03f6c779e0ac4ba9f202a6cf5b2968dab) | test: retire the deflaked monitor and approval nodes | [sase-ns.6.6](sase-ns.6.6.md) | 2026-08-17 05:25:58 EDT |

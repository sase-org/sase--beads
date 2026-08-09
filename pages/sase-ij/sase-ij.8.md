# Bead: sase-ij.8 — Merge sase-core release PRs from the release-plz workflow

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.8` · **Size:** small
**Created:** 2026-08-09 15:21:16 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

core-automerge: add a guarded job to sase-core's release-plz.yml that waits for the release PR's checks and squash-merges it, collapsing a median 43-minute and worst-case 9h36m human wait into roughly ten minutes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.8/README.md) | [sase-ij.8](sase-ij.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@735a01b`](https://github.com/sase-org/sase-core/commit/735a01b35143a5208af83451af31996a325fd755) | ci(release-plz): auto-merge release PRs once checks pass | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:31:05 EDT |
| sase-core | [`sase-core@443f1aa`](https://github.com/sase-org/sase-core/commit/443f1aa16994eb840c032e99df449170f22c722e) | fix(release-plz): set GH\_REPO in the merge job's gh commands | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:44:57 EDT |

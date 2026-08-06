# Bead: sase-fq.6 — Fix the silent 2s commit-log budget in sase-core

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.6` · **Size:** medium
**Created:** 2026-08-05 21:06:10 EDT · **Closed:** 2026-08-05 21:34:41 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

core-commit-budget: replace the hard, silently-empty two-second git log budget in the artifact-ref commit inventory with a generous and overridable one, land it in sase-core, and get a release published.

## Dependencies

- **Blocks:** [sase-fq.7](sase-fq.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.6/README.md) | [sase-fq.6](sase-fq.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0aba3c7`](https://github.com/sase-org/sase-core/commit/0aba3c76add2e5a92e8d60d175394e88af9cdd1a) | fix(editor): stop a slow git log from silently emptying the commit inventory | [sase-fq.6](sase-fq.6.md) | 2026-08-05 21:35:24 EDT |

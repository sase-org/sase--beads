# Bead: sase-177.1 — Muse runs synchronously behind a sunset flag, with a single-turn directive

[Bead Pages](../README.md) / [sase-177](README.md) / sase-177.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qc--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qc.md) · **Assignee:** `sase-177.1` · **Size:** medium
**Created:** 2026-09-23 17:47:07 EDT
**Plan:** [202609/muse\_single\_turn\_normalization.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_single_turn_normalization.md)

## Description

muse-shell: add the muse_synchronous_shell sunset flag; when on, launch muse exec with --enable-shell-tool (never duplicated from extra-args env); prefix every Muse prompt with a mode-aware single-turn directive stating the 10-minute ceiling and up-front routing rules; test both flag states; document in docs/llms.md.

## Dependencies

- **Blocks:** [sase-177.2](sase-177.2.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-177.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-177.1/README.md) | [sase-177.1](sase-177.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`28b3c1b`](https://github.com/sase-org/sase/commit/28b3c1bab27cdbbc6f1ea99c4f5afbebcbd003a4) | feat(muse): run synchronously behind muse\_synchronous\_shell sunset flag | [sase-177.1](sase-177.1.md) | 2026-09-23 18:09:21 EDT |

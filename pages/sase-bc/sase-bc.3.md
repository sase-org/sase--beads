# Bead: sase-bc.3 — Commit/artifact event capture, detached runner, notifications

[Bead Pages](../README.md) / [sase-bc](README.md) / sase-bc.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bc.3` · **Size:** medium
**Created:** 2026-07-30 17:33:25 UTC · **Closed:** 2026-07-30 18:46:58 UTC
**Plan:** [202607/commit\_file\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_file_hooks.md)

## Description

hooks-engine: capture per-file ADD/MODIFY/REMOVE events at both commit seams (CommitWorkflow and commit_sdd_files) and at `sase artifact create`, match them against configured file_hooks, execute matched commands once per file in a detached batch runner (`sase file-hook exec-batch`), and send a sase notification per run with attached output; never gate or slow the commit.

## Notes

[2026-07-30T18:46:58Z · sase-bc.3] Implemented commit and artifact ADD/MODIFY/REMOVE capture, deterministic detached file-hook batches, hidden exec-batch runner with timeout/idempotency/pruning, and success/failure notifications with attached logs. Verified focused engine/workflow/SDD/artifact/CLI tests (91 passed), isolated regression checks (18 passed), hidden CLI help, git diff --check, and full just check including 24,485-item pytest suite.

## Dependencies

- **Depends on:** [sase-bc.2](sase-bc.2.md) ✓
- **Blocks:** [sase-bc.4](sase-bc.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bc.3/README.md) | [sase-bc.3](sase-bc.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`f40c517`](https://github.com/sase-org/sase/commit/f40c517bfc7d0421d2a8df1fabb526b21964278e) | feat(file-hooks): run hooks for committed files | [sase-bc.3](sase-bc.3.md) | 2026-07-30 18:48:18 |

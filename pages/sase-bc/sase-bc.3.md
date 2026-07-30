# Bead: sase-bc.3 — Commit/artifact event capture, detached runner, notifications

[Bead Pages](../README.md) / [sase-bc](README.md) / sase-bc.3

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bc.3` · **Size:** medium
**Created:** 2026-07-30 17:33:25 UTC
**Plan:** [202607/commit\_file\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_file_hooks.md)

## Description

hooks-engine: capture per-file ADD/MODIFY/REMOVE events at both commit seams (CommitWorkflow and commit_sdd_files) and at `sase artifact create`, match them against configured file_hooks, execute matched commands once per file in a detached batch runner (`sase file-hook exec-batch`), and send a sase notification per run with attached output; never gate or slow the commit.

## Dependencies

- **Depends on:** [sase-bc.2](sase-bc.2.md) ✓
- **Blocks:** [sase-bc.4](sase-bc.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bc.3/README.md) | [sase-bc.3](sase-bc.3.md) | 0 |

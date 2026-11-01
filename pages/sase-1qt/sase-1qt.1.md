# Bead: sase-1qt.1 — Fix the apollo-only ACE prompt-render and hint failures (sase-1ia, sase-1l3, sase-1hy)

[Bead Pages](../README.md) / [sase-1qt](README.md) / sase-1qt.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.land.md) · **Assignee:** `sase-1qt.1` · **Size:** large
**Created:** 2026-11-01 18:08:20 EST
**Plan:** [202611/task\_backlog\_epic\_5.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_5.md)

## Description

apollo-prompt-render: the ACE prompt-render and hint widget tests behind sase-1ia, sase-1l3 and sase-1hy fail deterministically on apollo (7-9 failed of 30 across four files at sase 31a28d9618) and pass 30/30 on athena. Bisect the apollo host input that changes the result, fix it where it is owned (test isolation or product code), and prove the four files pass on both hosts without weakening an assertion.

## Notes

[2026-11-01T23:16:35Z · sase-1qt.1] PLANNING EVIDENCE: At clean sase HEAD 9066546900, _ArtifactFileCache.select_prompt_file still admits raw_prompt.md and sorts only by descending st_mtime_ns. A mocked-filesystem probe of the real method selects raw at equal mtimes with raw-first enumeration, selects expanded when enumeration reverses, and selects raw again when its mtime is newer. This confirms a product precedence defect; apollo candidate timestamps/order still need measuring before asserting the exact host trigger. The four primary files pass on athena (Python 3.14.7, pytest -q -n 0 -p no:cacheprovider): 30 passed in 4.54s. No implementation changes made. Authored and validated a medium tale for Rust-owned selection policy, Python cache integration, deterministic tie/raw-exclusion regressions, and cross-host verification. No epic-symbol entries currently reference this phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qt.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.1.md) | [sase-1qt.1](sase-1qt.1.md) | 0 |

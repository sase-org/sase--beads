# Bead: sase-1qt.1 — Fix the apollo-only ACE prompt-render and hint failures (sase-1ia, sase-1l3, sase-1hy)

[Bead Pages](../README.md) / [sase-1qt](README.md) / sase-1qt.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qn.land.md) · **Assignee:** `sase-1qt.1` · **Size:** large
**Created:** 2026-11-01 18:08:20 EST · **Closed:** 2026-11-01 20:44:44 EST
**Plan:** [202611/task\_backlog\_epic\_5.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_5.md)

## Description

apollo-prompt-render: the ACE prompt-render and hint widget tests behind sase-1ia, sase-1l3 and sase-1hy fail deterministically on apollo (7-9 failed of 30 across four files at sase 31a28d9618) and pass 30/30 on athena. Bisect the apollo host input that changes the result, fix it where it is owned (test isolation or product code), and prove the four files pass on both hosts without weakening an assertion.

## Notes

[2026-11-01T23:16:35Z · sase-1qt.1] PLANNING EVIDENCE: At clean sase HEAD 9066546900, _ArtifactFileCache.select_prompt_file still admits raw_prompt.md and sorts only by descending st_mtime_ns. A mocked-filesystem probe of the real method selects raw at equal mtimes with raw-first enumeration, selects expanded when enumeration reverses, and selects raw again when its mtime is newer. This confirms a product precedence defect; apollo candidate timestamps/order still need measuring before asserting the exact host trigger. The four primary files pass on athena (Python 3.14.7, pytest -q -n 0 -p no:cacheprovider): 30 passed in 4.54s. No implementation changes made. Authored and validated a medium tale for Rust-owned selection policy, Python cache integration, deterministic tie/raw-exclusion regressions, and cross-host verification. No epic-symbol entries currently reference this phase.

[2026-11-02T01:44:20Z · sase-1qt.1--2] TASK RESOLVED sase-1ia/sase-1l3/sase-1hy. Measured root cause on apollo (ext4 /tmp): 28/30 consecutive raw+expanded fixture writes share one mtime tick and readdir returns raw-first, so the old newest-mtime+stable-sort policy selected raw_prompt.md (athena tmpfs /tmp ties 30/30 too but readdir returns 01_prompt.md first, so it passed by luck). Fix: new sase_core agent_prompt_selection policy (excludes canonical+legacy raw and commit_finalizer_pass_* re-prompts, newest integer-ns mtime wins, ties prefer lexicographically greatest path, workflow -step_name preference with fallback) exposed as agent_prompt_select binding (wire schema v1); artifact_files_cache.select_prompt_file now delegates via require_rust_binding with no Python fallback. Verification: Rust 9 core + 4 binding tests pass; sase-core check green; athena before 30/30 at clean HEAD a79207993c and after 128/128 (4 primary files + 7 siblings + cache tests + macro-terminology); apollo before 7 failed/23 passed (same 4 files, -n 4, Python 3.12 venv, before-wheel from clean tree) and after 118/118 with after-wheel sha256 c391ce7a... (binding verified); new forced-tie+reversed-order e2e regression fails on reverted code (demonstrated) and passes with the fix.

[2026-11-02T01:44:28Z · sase-1qt.1--2] sase-1i9 recheck PASS on both hosts (athena single-node 1 passed; apollo inside the 118-passed after run).

[2026-11-02T01:44:32Z · sase-1qt.1--2] PROPOSED FOLLOW-UP: the sase-core wheel cache stored wheel 86beb74a (18:56 EST) built without the working-tree agent_prompt_select binding (0 string refs; fresh maturin build has 5) — store/lookup identity vs dirty-tree handling needs owner review; after-wheel for apollo was a direct maturin build instead.

[2026-11-02T01:44:44Z · sase-1qt.1--2] sase-1qt.1 done. sase-1ia/-1l3/-1hy resolved by Rust-owned prompt-selection policy; 4 primary files + 7 siblings + cache tests pass on athena (128) and apollo (118); sase-1i9 passes both hosts; sase + sase-core checks green.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qt.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.1.md) | [sase-1qt.1](sase-1qt.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@45c6a26`](https://github.com/sase-org/sase-core/commit/45c6a2601bb8fdaa48180ba97caa6339fe0a35c5) | feat(agent-prompts): add Rust-owned agent prompt selection policy | [sase-1qt.1](sase-1qt.1.md) | 2026-11-01 20:45:43 EST |
| sase | [`d26baec`](https://github.com/sase-org/sase/commit/d26baecb051927df38a8bfe4683b7d509371b1d1) | fix(agent-prompts): delegate prompt selection to Rust agent\_prompt\_select binding | [sase-1qt.1](sase-1qt.1.md) | 2026-11-01 20:46:50 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qt.1--2][1] | Closeout read before noting and closing tale | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qt.1.md

<!-- sase:referenced-by:end -->

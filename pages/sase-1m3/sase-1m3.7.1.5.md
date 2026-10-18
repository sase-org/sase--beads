# Bead: sase-1m3.7.1.5 — Tokei dependency gate and performance evidence

[Bead Pages](../README.md) / [sase-1m3.7.1](sase-1m3.7.1.md) / sase-1m3.7.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1m3.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.md) · **Assignee:** `sase-1m3.7.1.5` · **Size:** medium
**Created:** 2026-10-17 02:56:52 EDT · **Closed:** 2026-10-18 18:09:46 EDT
**Plan:** [202610/project\_stats\_code\_records.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_stats_code_records.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:6779f88bc85f208e69e02940 | attached via sase artifact create --bead |
| related | file:explicit:cf0a3ec863e10c52c0785b78 | attached via sase artifact create --bead |
| related | file:explicit:ea24bb0b3953dc8daa075f39 | attached via sase artifact create --bead |
| related | file:explicit:f8fc12f54cb3f9b647451035 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

measurement: evaluate tokei against the integrated nonblank baseline, measure cold and incremental snapshots on sase, and assemble compatibility and completion evidence for sase-1m3.7.

## Notes

[2026-10-18T15:38:40Z · sase-1m3.7.1.5] MEASUREMENT CHECKPOINT: Prepared isolated nonblank and tokei 15.0.0 source trees from integrated core 80dc704a4f2e1f640f7caa9e578957669c31367d. No production dependency decision yet. Exact preparation/build scripts and staged trees are under the opened core checkout .git/project-stats-measurement/. Paired clean release builds use the same Python, target, strip settings and four jobs; downloads/hakari are outside timing. A monitor continuation will evaluate the measured gate, finish snapshot/binding evidence, run required checks, and close only this phase.

[2026-10-18T15:44:52Z · sase-1m3.7.1.5--1] MEASUREMENT CHECKPOINT: Monitor 6c3jxk8tn59q stopped before compilation because cargo install rejected the bare version 0.9. Corrected the experiment-only wrapper to the explicit range ^0.9 in both archives and prepare.py; bash syntax and Python compilation checks pass. Preserved the failed preparation log in install-hakari-attempt-1.log and its report entry. No release measurements exist yet, no production changes, and no dependency decision. Resuming the same build_pair.py with --resume through SASE monitor.

[2026-10-18T16:52:54Z · sase-1m3.7.1.5--2] MEASUREMENT CHECKPOINT: Paired clean release wheels passed the tokei gate: 22,278,674 to 22,445,311 bytes (+166,637 bytes / 0.159 MiB), 1,611.196 to 1,578.330 seconds (0.980x). Adopted tokei 15.0.0 without default features in the linked core checkout, with explicit config, language-keyed blob counts, versioned cache/fingerprint identity, source/tests SLOC, and nonblank prose/data. Dependency/hakari parity and fmt pass. Production tests/release binding benchmarks/check are next under a monitor. Prototype on sase tree c4299924ba07377277914e4c7b6304b3f1ec90e7 (14,477 files): same-tip 35 ms; cold 5.8–7.3 s; changed-tip 630 ms. Nonblank changed-tip was 616 ms. Final production measurements will supersede prototype figures after skipping unnecessary prose parsing.

[2026-10-18T17:06:51Z · sase-1m3.7.1.5--3] MEASUREMENT CHECKPOINT: Monitor n350m0gkm04q ran the project-statistics tests: 124 passed, two ignored, one new assertion failed. Independent queries against the measured tokei wheel and upstream v15 source confirmed single-line Python triple-quoted strings count as code despite the docstring option; tests now pin that limitation and separately check multiline docstrings. Also fixed a real lowercase language-hint bug by using the case-insensitive FromStr parser, so extensionless shebang scripts do not fall through to Text/zero. Counter cache identity advanced to v2. Core fmt passed. Primary revision ratchet applied 07bfb83f (documented exit 2); host finalization must pin the new core commit when both dirty repos are declared. Resuming targeted tests, release binding and benchmarks through monitor; whole-repo checks follow explicitly.

[2026-10-18T17:07:45Z · sase-1m3.7.1.5--3] PROPOSED FOLLOW-UP: Refresh generated sase_artifact skill — the deployed SKILL.md still documents -n for labels and says create moves the source; the audited sase_artifacts memory and current CLI use -l and copy by default. No memory or skill files edited in this phase.

[2026-10-18T17:58:26Z · sase-1m3.7.1.5--4] PROPOSED FOLLOW-UP: Project Code cold and changed-tip runtime budgets remain unmet — final release wheel on sase tree c4299924ba07377277914e4c7b6304b3f1ec90e7 (14,477 tracked / 12,432 code files) measured cold 7.628 s (fixture 6.397 s; new-tip cold 8.571 s), changed-tip 0.922 s, and same-tip median 37.187 ms. Separate audit proved 13,249 unique cold blobs, zero same-tip reads, and exactly one changed-tip blob with whole-result cold equality. The lower-load nonblank baseline also missed changed-tip (0.616 s), versus prototype SLOC 0.630 s; final host load was 12.3–14.4 on 16 vCPUs. Instrumented changed-tip Git time was 0.575 s, dominated by ls-tree 0.177 s and committed attributes 0.336 s, with cat-file only 0.005 s. Cold parser work adds substantial cost beyond shared Git/query work; audit wrapper timings are not uninstrumented latency. Production already avoids SLOC parsing of noncode roles. Follow-up should profile/bound tree, attribute and snapshot-cache reconstruction plus cold parser cost without weakening classification or blob-read correctness. Final report and raw evidence will be attached before closure.

[2026-10-18T18:23:22Z · sase-1m3.7.1.5--4] PROPOSED FOLLOW-UP: Corroborate existing gateway IPC flake sase-1gz — required core ToolRun eb497afb7f740fc9341d6fe799f57732 exited 101 after fmt/features/clippy, core library/integration tests and Python binding tests passed. Its sole failure was listener_creates_private_socket_and_rejects_symlink at ipc.rs:42: unexpected AlreadyRunning for the temporary worker.sock. The exact test passed immediately in isolation on the unchanged tree via just test -p sase_gateway listener_creates_private_socket_and_rejects_symlink. Audited sase-1gz has independent preexisting same-node/same-error witnesses, including c89d5c356878cea3f27ca1ba02894cd5 on 2026-10-10 and 6073ab9106d5cf969d698ea04884f008; no gateway source was edited here. Completing the gateway/LSP/doctest/script lanes omitted by fail-fast, preserving the original exit 101 and diagnostics. No new bead created.

[2026-10-18T18:30:34Z · sase-1m3.7.1.5--4] VERIFICATION UPDATE: The unchanged-tree wrapped core retry 1b69537c51496b32559ca24cfe13dca1 passed all stages in 321.443 s, after initial run eb497afb7f740fc9341d6fe799f57732 hit tracked socket flake sase-1gz. Full gateway/LSP tests, workspace doctests and script tests also passed separately. Initial exit 101 remains preserved in the evidence; no test assertion or gateway source was changed. Primary check 7bef757b7517b65fc8821fa811fddb88 is still finishing its automatically requested release binding build.

[2026-10-18T18:33:45Z · sase-1m3.7.1.5--4] GATE CORRECTION — supersedes the clean-time PASS claims in notes #3/#4 and file:explicit:6779f88bc85f208e69e02940. Auditing the actual Cargo layout revealed build_pair.py overrides CARGO_TARGET_DIR but inherits CARGO_BUILD_BUILD_DIR. Both staged target directories contain final artifacts but no deps/fingerprint directories; the candidate log compiles only 106 packages versus baseline 206 and omits proc-macro2, demonstrating shared intermediate reuse. The wheel-size delta remains a valid equivalent-wheel observation, but 1611.196/1578.330 seconds and 0.980x are NOT independent clean build measurements and cannot authorize adoption. Prepared build_pair_isolated.py to use fresh target-isolated-{nonblank,tokei} and explicitly set each CARGO_BUILD_BUILD_DIR to its own target/build, record both paths and assert fingerprint evidence. Old evidence is preserved. Repeat is required to repair experimental isolation, not an unnecessary repeat of successful clean builds. Production tokei remains provisional until both corrected thresholds pass; do not close this phase or publish the draft final report using the old gate.

[2026-10-18T19:59:25Z · sase-1m3.7.1.5--4] VERIFICATION: primary ToolRun 7bef757b7517b65fc8821fa811fddb88 completed exit1: 56389 passed, 33 skipped, 21 failed; all preceding gates passed. Triage has13 independently witnessed KNOWN groups and4 NEW TUI groups (session detached hints, clan prompt precedence, update toast, bottom pinning). No TUI edits in this phase. Full diagnostics retained in the phase experiment; preparing focused current versus clean-primary/nonblank-binding comparisons before classifying the new failures. Core whole retry1b69537c51496b32559ca24cfe13dca1 passed. Corrected isolated build gate is still pending; old timing remains withdrawn under file:explicit:ea24bb0b3953dc8daa075f39. No claim that primary verification or the corrected gate passed.

[2026-10-18T20:46:54Z · sase-1m3.7.1.5--5] MEASUREMENT RECOVERY: monitor q5amscwxdafk failed before tests/builds because tools/run_pytest rejects -n 0 (exit 4). Fixed experiment-only runner to use supported SASE_PYTEST_WORKERS=1, resume the existing source archive, retain attempt logs and write JUnit. Both current and clean-primary/pre-phase-nonblank inputs now collect all 21 nodes successfully with verified import origins; test outcomes remain pending. Baseline caveat is explicit: original primary core pin differs from integrated nonblank baseline only under project_stats, so this is a clean-primary/pre-phase-core comparison. Production digest remains 7d63e2ef364a9388d1f9f7136407b2718515faa089558f7c7b77bdeca4ae9735. Host disk fell below 2 GiB; removed only obsolete experiment targets and unpacked wheel copies, retaining all wheel archives/results/logs. Corrected gate will wait outside timing for 4 GiB before each isolated build, bounded to 30 minutes per preflight. Old timing remains invalid; no adoption or completion claim.

[2026-10-18T22:05:20Z · sase-1m3.7.1.5--6] PROPOSED FOLLOW-UP: Primary TUI failures corroborated independently of the counter change — original check 7bef757b7517b65fc8821fa811fddb88 remains exit 1 (56,389 passed, 33 skipped, 21 failed). Thirteen groups covering 17 nodes already have independent KNOWN witness runs. Focused one-worker current versus clean-primary/pre-phase nonblank-core probes completed exit 1 with 14 failed/7 passed and 16 failed/5 passed. Three initially NEW nodes reproduce identical tracebacks after normalizing only temporary pytest paths and object addresses: test_session_collapsed_detached_macro_skips_markers (file_hints retains detached raw prompt), test_member_loader_reuses_reply_and_prompt_precedence (raw rather than expanded prompt), and test_bottom_pinned_body_stays_pinned_across_row_count_change (pin lost). The fourth NEW node, test_startup_update_toast_appears_once_in_tui, passes both focused retries without source edits; narrower selection/worker count prevents claiming identical environment or a root cause. Baseline caveat: clean primary HEAD plus integrated nonblank core 80dc704, whose runtime matches clean 07bfb83; original pin 72bf92

… and 2525 more characters

## Dependencies

- **Depends on:** [sase-1m3.7.1.4](sase-1m3.7.1.4.md) ✓ · ⧖ 2026-10-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.7.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.5.md) | [sase-1m3.7.1.5](sase-1m3.7.1.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b8737fa`](https://github.com/sase-org/sase-core/commit/b8737fa56f9367f60f28ecd35cfd8bc9369efb27) | feat(stats): count committed source lines with tokei | [sase-1m3.7.1.5](sase-1m3.7.1.5.md) | 2026-10-18 18:14:45 EDT |
| sase | [`5fe54b5`](https://github.com/sase-org/sase/commit/5fe54b59745c9351702b8df667eb99fc927e8911) | feat(stats): advance core pin for measured SLOC snapshots | [sase-1m3.7.1.5](sase-1m3.7.1.5.md) | 2026-10-18 18:20:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.7.1.5--6][1] | Check final closure notes before recovery finalization | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.7.1.5.md

<!-- sase:referenced-by:end -->

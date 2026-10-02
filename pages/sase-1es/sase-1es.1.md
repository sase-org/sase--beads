# Bead: sase-1es.1 — Pager benchmark and baseline

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.1` · **Size:** small
**Created:** 2026-10-02 08:37:45 EDT · **Closed:** 2026-10-02 09:05:51 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

pager-bench: add a subprocess-isolated pager benchmark over a synthetic corpus (open, keys, search, memory, leak, cold import, CLI wall time), a fast smoke test, and recorded baseline numbers.

## Notes

[2026-10-02T13:05:35Z · sase-1es.1] Baseline (master, shared host, 2026-10-02; noisy — do not treat as committed gates). Harness: tests/perf/bench_pager.py + _pager_bench_corpus.py, smoke test_pager_bench_smoke.py, just bench-pager, README Pager section. 500 lines code-sparse: mount 1.98s wall, syntax-publish 1.98s, RSS 268MB. 2000 lines: code-sparse mount 8.13s/syntax 8.13s/RSS 607MB; log-dense mount 10.44s/RSS 700MB; markdown mount 8.20s/syntax 8.20s/RSS 595MB. Nav keys (j/k/ctrl+d/G/g) ~10ms CPU at 2k (near 12ms trivial-app floor); label-a key 0.24-1.71s CPU; search chars 0.1-0.5s CPU. Leak probe: 1 of 3 pushed PagerViews still live after gc at every size (confirms the scan-leak-fixes target). Cold: import sase.main.pager_handler 1.56s, sase.pager.screen 1.57s; pager --plain file 2.33s (rc 0); pty first-bytes 0.02s (proxy: counts terminal-init bytes, not content paint); plain-bead run SKIPPED (no disposable SASE_HOME bead-store fixture). Verified: smoke 2 passed; slow matrix (7 corpora x 500, subprocess-isolated) passed; CLI 2k + cold runs ok end to end, no hangs (per-case timeouts, TIMEOUT reported not hung).

[2026-10-02T13:05:51Z · sase-1es.1] Delivered bench_pager.py (slow, subprocess-isolated, per-case timeouts), _pager_bench_corpus.py (7 deterministic corpora, 500/2k/20k/100k ladder), non-slow smoke test, just bench-pager recipe, README Pager section. Verified: smoke 2 passed, slow matrix 7x500 passed, CLI 2k + cold probes ran end to end with no hangs; baseline recorded in bead notes; epic-symbols clean.

[2026-10-02T14:15:19Z · sase-1es.1--2] Verification after monitored just check runs: lint-test-waits UNKNOWN failure on tests/perf/bench_pager.py:414 (fixed-sleep-missing-pragma) repaired by adding pragma "# sase-test-wait: pty quit drain"; just _lint-test-waits now exits 0. Full just check escalated to full suite: 7 failures, all KNOWN with witnesses (test_force_reuse_launch_seam_consume/rejection/registry x6 + test_app_import_budget x1), none touching pager bench files. PROPOSED FOLLOW-UP: the 7 KNOWN failures remain for the land agent to triage at epic close.

## Dependencies

- **Blocks:** [sase-1es.2](sase-1es.2.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.3](sase-1es.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.4](sase-1es.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.1.md) | [sase-1es.1](sase-1es.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cca547`](https://github.com/sase-org/sase/commit/6cca547014bdb14afcaa80db5a772af29f3460aa) | feat(pager): add subprocess-isolated pager benchmark with baseline | [sase-1es.1](sase-1es.1.md) | 2026-10-02 10:27:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1es.1--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1es.1.md

<!-- sase:referenced-by:end -->

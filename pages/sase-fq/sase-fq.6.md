# Bead: sase-fq.6 — Fix the silent 2s commit-log budget in sase-core

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.6` · **Size:** medium
**Created:** 2026-08-05 21:06:10 EDT · **Closed:** 2026-08-05 21:34:41 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

core-commit-budget: replace the hard, silently-empty two-second git log budget in the artifact-ref commit inventory with a generous and overridable one, land it in sase-core, and get a release published.

## Notes

[2026-08-06T02:27:52Z · sase-fq.6] PROPOSED FOLLOW-UP: confirm R6 from a real CI run — the new stderr diagnostic names why a repository is dropped, so the next occurrence of the empty artifact-ref commit inventory should be read from the CI log rather than re-hypothesized. Local stress (32x CPU oversubscription on 2 cores plus a concurrent dd IO storm) never pushed `git log` past 261ms, so the 2s budget was never proven to be the CI cause; spawn EAGAIN and tempfile EMFILE are equally plausible and are now reported distinctly.

[2026-08-06T02:28:20Z · sase-fq.6] RELEASED: sase-core-rs 0.18.2 (GitHub release v0.18.2, live on PyPI with 5 files) — this is the version sase-fq.7 should pin. sase-core commits: 0aba3c7 (fix) and 8785320 (test flake fix).

Mechanism confirmed deterministically: commit_log_output's budget expiry makes a repository contribute zero rows, which is exactly the () the sase parity test saw. Tests wedge git with an include.path pointing at a writerless FIFO so it blocks during start-up config parsing; a merely tiny budget is not deterministic because a healthy git log can exit before the first poll.

Fix: default budget 2s -> 30s, overridable via SASE_ARTIFACT_REF_COMMIT_TIMEOUT (positive finite seconds; malformed/absent falls back). The collapsed Option is now a CommitLogFailure naming scratch-file / spawn / budget / wait / exit-status / read, reported on stderr per the existing parse_prompt_artifact_manifest convention, so a dropped repository is no longer silent.

Verified: cargo fmt --check, cargo clippy --workspace --all-targets -D warnings, and cargo test --workspace clean 20/20 consecutive runs. sase-core CI green on both commits and on release PR #85. Against the published 0.18.2 wheel in this workspace, tests/ace/tui/widgets/test_artifact_ref_completion_catalog.py passes (5 passed), and SASE_ARTIFACT_REF_COMMIT_TIMEOUT=0.000001 reproduces the exact CI failure shape with the new diagnostic naming the budget.

Also fixed en route: four host-bridge/gateway tests exec'd a freshly written script and lost an ETXTBSY race against sibling threads' forks (~1 run in 8 locally; it failed the first release-PR CI leg). They now run the script through /bin/sh instead of chmod+exec.

## Dependencies

- **Blocks:** [sase-fq.7](sase-fq.7.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.6/README.md) | [sase-fq.6](sase-fq.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0aba3c7`](https://github.com/sase-org/sase-core/commit/0aba3c76add2e5a92e8d60d175394e88af9cdd1a) | fix(editor): stop a slow git log from silently emptying the commit inventory | [sase-fq.6](sase-fq.6.md) | 2026-08-05 21:35:24 EDT |
| sase-core | [`sase-core@8785320`](https://github.com/sase-org/sase-core/commit/8785320e186a7115ea003ae2eef70fa26365aedd) | test(host-bridge): stop exec-ing freshly written helper scripts | [sase-fq.6](sase-fq.6.md) | 2026-08-05 21:58:49 EDT |

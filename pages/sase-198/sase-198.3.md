# Bead: sase-198.3 — Core pin bump, end-to-end directive tests, and docs

[Bead Pages](../README.md) / [sase-198](README.md) / sase-198.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1n.md) · **Assignee:** `sase-198.3` · **Size:** small
**Created:** 2026-09-25 09:49:04 EDT · **Closed:** 2026-09-25 13:09:31 EDT
**Plan:** [202609/queue\_zero\_weight.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_zero_weight.md)

## Description

pin-e2e-docs: move sase-core-revision.txt past the core-contract commit, add directive-level tests that exercise %q(w=0) through the real Rust binding, and update the user docs and config text that say weight must be positive.

## Notes

[2026-09-25T17:08:28Z · sase-198.3--1] PROPOSED FOLLOW-UP: `sase validate` agent-prompts check fails identically on clean base tree (4 errors: artifact-untracked 412ed4ed + 3 artifact-missing in prompts/202608/bbugyi200.athena.0g6.md, prompts/202609/0gr.md, prompts/202609/0lb.md); pre-existing, unrelated to sase-198.3 pin/tests/docs diff

[2026-09-25T17:09:31Z · sase-198.3--1] pin c31b8cf; e2e %q(w=0) tests green incl. epic-monitor non-inheritance (120 passed in touched files); docs/config updated. Full-gate SASE validation
  ok     doctor plugins.required
  ok     init memory --check
  ok     init repo --check
  ok     init skills --check
  ok     doctor config.file_hooks
  ok     plan links validate
  fail   agent prompts validate

Warnings:
  init skills: 56 provider skill files out of sync with rendered sources; redeploy is deferred until land. Rerun `sase init skills` after landing.

agent prompts validate failed (exit 1)
stderr:
Prompt archive validation failed: 4 errors, 55 warnings (use --show-warnings to 
display)
error: 
files/objects/sha256/41/412ed4ed462f3f76938f9846b24973ee9d2783d09fa7a3e747e24dd2
581b6268: prompt-linked archive object is not tracked by git 
(artifact-untracked)
error: prompts/202608/bbugyi200.athena.0g6.md: published artifact target does 
not exist: 
../../files/objects/sha256/40/40de62d889bdb2a7cbf17a5fcaf86d0913c5f07b794eb7561a
98d2df10bda5bb (artifact-missing)
error: prompts/202609/0gr.md: published artifact target does not exist: 
../../files/objects/sha256/5b/5bd2b6fd34a08c1ef53cdadbc2a759340118ec0fd0d9e260f2
48f73309a28cf3 (artifact-missing)
error: prompts/202609/0lb.md: published artifact target does not exist: 
../../files/objects/sha256/41/414a92e8e104e8131ae51a48d7cece6e8f1410f6f76bf97ee7
d3a2a5b79e02c8 (artifact-missing)

For broader diagnostics, run `sase doctor -v` or `sase doctor -j` and attach the output when asking for help. agent-prompts failure reproduces identically on clean base tree (pre-existing, recorded as follow-up)

## Dependencies

- **Depends on:** [sase-198.1](sase-198.1.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-198.2](sase-198.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-198.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.3.md) | [sase-198.3](sase-198.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0607f7a`](https://github.com/sase-org/sase/commit/0607f7a083d80a96d3b1e9e0b5d6174417a6ce4e) | feat(queue): allow zero-load agents with %queue(weight=0) (sase-198.3) | [sase-198.3](sase-198.3.md) | 2026-09-25 13:12:21 EDT |

# Bead: sase-zs.3 — Deterministic retryability classifier in the Rust core

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.3` · **Size:** medium
**Created:** 2026-09-12 09:44:51 EDT · **Closed:** 2026-09-12 10:39:22 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

classifier: port transient-failure detection for git and `gh` output into sase_core as a pure deterministic classifier with a PyO3 binding, replacing the ad-hoc substring tuple that only covers git clone stderr.

## Notes

[2026-09-12T14:38:53Z · sase-zs.3] PROPOSED FOLLOW-UP: Update the core pin after the core stitch exists — main now calls classify_failure_retryability, so the land agent must ratchet sase-core-revision.txt to the committed core SHA before landing main CI.

[2026-09-12T14:39:22Z · sase-zs.3] Implemented pure Rust git/gh retryability classifier with PyO3 binding and Python facade; routed SDD clone transient detection through it. Verified cargo fmt, focused Rust retryability tests, rebuilt local PyO3 binding, focused Python retryability tests, core just check with PYO3_PYTHON/LD_LIBRARY_PATH, main just check (full-suite escalation), and epic-symbol audit for sase-zs.3.

## Dependencies

- **Blocks:** [sase-zs.5](sase-zs.5.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zs.6](sase-zs.6.md) ◐ · ⧖ 2026-09-12
- **Blocks:** [sase-zs.8](sase-zs.8.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.3/README.md) | [sase-zs.3](sase-zs.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`186c543`](https://github.com/sase-org/sase/commit/186c543d0e79e0518a7da20a96754dd7295ea3da) | feat(github): add retryability classifier facade | [sase-zs.3](sase-zs.3.md) | 2026-09-12 10:40:55 EDT |

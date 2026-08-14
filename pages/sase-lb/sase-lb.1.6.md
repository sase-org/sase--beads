# Bead: sase-lb.1.6 — The commit finalizer stops attributing pre-existing dirt to the agent

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.6` · **Size:** medium
**Created:** 2026-08-14 11:11:19 EDT · **Closed:** 2026-08-14 11:59:46 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

finalizer: capture a dirty-path baseline at runner start and exclude those paths from the finalizer's must-commit set, reporting them as pre-existing instead.

## Notes

[2026-08-14T15:59:46Z · sase-lb.1.6] Implemented dirty-path baseline capture at runner start (commit_finalizer_baseline.py) and wired exclusion of pre-existing dirty paths into commit_finalizer_state.py/commit_finalizer_prompting.py, reported as pre-existing instead of attributed to the agent. Verified: 571 existing commit-finalizer tests pass unchanged (byte-identical behavior with no baseline present), 16 new baseline unit tests pass, new bootstrap wiring test passes, and full 'just check' (fmt, ruff, mypy, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig, SASE validation, scoped tests) exits 0.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.6/README.md) | [sase-lb.1.6](sase-lb.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`645875d`](https://github.com/sase-org/sase/commit/645875d536b9f5f92f0b9fc59eda28e0b2640aa4) | fix(llm\_provider): stop attributing pre-existing dirt to the agent | [sase-lb.1.6](sase-lb.1.6.md) | 2026-08-14 12:00:26 EDT |

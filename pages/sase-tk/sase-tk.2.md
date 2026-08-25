# Bead: sase-tk.2 — SASE admission regressions and documentation

[Bead Pages](../README.md) / [sase-tk](README.md) / sase-tk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0dd](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0dd.md) · **Assignee:** `sase-tk.2` · **Size:** small
**Created:** 2026-08-25 08:40:52 EDT · **Closed:** 2026-08-25 10:41:37 EDT
**Plan:** [202608/claimed\_workspace\_if.md](https://github.com/sase-org/sase--plans/blob/main/202608/claimed_workspace_if.md)

## Description

sase_regressions: exercise ordering, synchronization, cleanup, and failure behavior and document the revised typed-admission contract.

## Notes

[2026-08-25T14:38:14Z · sase-tk.2] PROPOSED FOLLOW-UP: existing Ruff F811 failure in src/sase/llm_provider/commit_finalizer_baseline.py — just check currently fails because FinalizerBaselineRecord is defined and then re-aliased in that module.

[2026-08-25T14:41:37Z · sase-tk.2] Added admission regressions and docs for project-scoped condition workspace leases. Verified: focused admission/condition suite passed (30 tests); ruff format/check passed on touched Python files; git diff --check passed; just check rerun still fails on unrelated Ruff F811 in src/sase/llm_provider/commit_finalizer_baseline.py, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-tk.1](sase-tk.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tk.4](sase-tk.4.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tk.2/README.md) | [sase-tk.2](sase-tk.2.md) | 0 |

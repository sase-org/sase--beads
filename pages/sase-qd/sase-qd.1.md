# Bead: sase-qd.1 — A verified write path for the current project

[Bead Pages](../README.md) / [sase-qd](README.md) / sase-qd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06w](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06w.md) · **Assignee:** `sase-qd.1` · **Size:** medium
**Created:** 2026-08-18 18:14:39 EDT · **Closed:** 2026-08-18 18:48:15 EDT
**Plan:** [202608/projects\_tab\_current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/projects_tab_current_project.md)

## Description

core-set: add `set_current_project()` to `sase.current_project` — eligibility check, provider-exact MRU prefix, single MRU promotion, post-write re-resolve — returning a typed outcome, and land `sase project set-current <project>` as its first real consumer.

## Notes

[2026-08-18T22:47:47Z · sase-qd.1] PROPOSED FOLLOW-UP: just check _lint-flags fails on this host because feature flags name missing beads sase-nw, sase-om, sase-pa, and sase-nx — independent of this phase; _lint-toobig also fails on pre-existing tests/_suite_gate.py (1197 lines).

[2026-08-18T22:48:15Z · sase-qd.1] Landed set_current_project() (eligibility, provider-exact MRU prefix, unchanged short-circuit that leaves st_mtime_ns untouched, one record_vcs_xprompt_usage write, post-write re-resolve) and sase project set-current <project> [-j|--json] (exit 0 for set/unchanged, 1 for ineligible/unverified). Retired the false no-set-command claim in parser help, docs/cli.md, docs/ace.md, and docs/configuration.md. Verified: unit tests for all four outcomes plus the vcs_kind/detect_workflow_type regression; CLI help/parser/handler tests; sase bead epic-symbols sase-qd.1 reports none; symvision clean; just test-scoped escalated (core-identity-changed) and the full suite passed 33772 with 13 skipped. just check still fails on pre-existing _lint-flags (missing sase-nw/om/pa/nx) and _lint-toobig (tests/_suite_gate.py), recorded as PROPOSED FOLLOW-UP.

[2026-08-18T22:49:36Z · sase-qd.1] Landed set_current_project() (eligibility, provider-exact MRU prefix, unchanged short-circuit that leaves st_mtime_ns untouched, one record_vcs_xprompt_usage write, post-write re-resolve) and sase project set-current <project> [-j|--json] (exit 0 for set/unchanged, 1 for ineligible/unverified). Retired the false no-set-command claim in parser help, docs/cli.md, docs/ace.md, and docs/configuration.md. Verified: unit tests for all four outcomes plus the vcs_kind/detect_workflow_type regression; CLI help/parser/handler tests; sase bead epic-symbols sase-qd.1 reports none; symvision clean; just test-scoped escalated (core-identity-changed) and the full suite passed 33772 with 13 skipped.

## Dependencies

- **Blocks:** [sase-qd.4](sase-qd.4.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qd.1/README.md) | [sase-qd.1](sase-qd.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce53444`](https://github.com/sase-org/sase/commit/ce534441fbcf47356f8628a52bd5619416990bcb) | feat(project): add set\_current\_project and sase project set-current | [sase-qd.1](sase-qd.1.md) | 2026-08-18 18:50:20 EDT |

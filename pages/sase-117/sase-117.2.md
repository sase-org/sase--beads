# Bead: sase-117.2 — Convergence fix

[Bead Pages](../README.md) / [sase-117](README.md) / sase-117.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0l7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0l7.md) · **Assignee:** `sase-117.2` · **Size:** medium
**Created:** 2026-09-15 09:49:39 EDT · **Closed:** 2026-09-15 11:56:17 EDT
**Plan:** [202609/ace\_family\_status\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202609/ace_family_status_convergence.md)

## Description

convergence-fix: stop dropping queued exact artifact dirs in fallback state, fix the mechanism Phase 1 pinned in the merge/token-accept/apply path, and turn the harness xfails green under the tui_perf acceptance criteria (no new refresh paths, quiet idle ticks, unchanged j/k p95).

## Notes

[2026-09-15T15:56:17Z · sase-117.2] Verified focused convergence/refresh suites green (82 passed), just fmt passed, just check passed (scoped selected 428 files), git diff --check clean, and sase bead epic-symbols sase-117.2 reported no entries.

## Dependencies

- **Depends on:** [sase-117.1](sase-117.1.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-117.4](sase-117.4.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-117.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-117.2/README.md) | [sase-117.2](sase-117.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0efad90`](https://github.com/sase-org/sase/commit/0efad90a2c1c4d5b7fb63d7f2e42188a061d47a8) | fix(ace): converge family status refresh | [sase-117.2](sase-117.2.md) | 2026-09-15 12:11:40 EDT |

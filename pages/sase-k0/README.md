# Bead: sase-k0 — Converge task bead gates and settle them the moment a bead closes

[Bead Pages](../README.md) / sase-k0

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yk/README.md) · **Assignee:** `sase-k0.land`
**Created:** 2026-08-12 10:58:32 EDT · **Closed:** 2026-08-12 14:53:47 EDT
**Plan:** [202608/task\_gate\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_gate_convergence.md)

## Description

Live TaskTriage/BeadSnooze notifications match the set of live task beads even after a project leaves the inventory or the chop's state file is lost, and closing a task bead from the CLI clears its gate notification immediately instead of up to five minutes later.

## Notes

[2026-08-12T18:53:47Z · sase-k0.4.land] LAND COMPLETE: Audited sase-k0 and every descendant, every child note, the durable plan, current source, and all five feature/landing commits. 07f050d3a adds the shared deterministic pending bead-gate resolver and routes TaskTriage lookup through it. 875f67b74 settles TaskTriage and BeadSnooze gates after successful task close with one scan and zero filesystem work for non-task/no-op closes. 95a9b4575 makes bead_task_triage sweep inactive-project state and producer-owned untracked gates while preserving unreadable projects and failing closed on unavailable inventory. 9960d7444 restores fresh-g1 and cross-project-key exact-convergence regressions. 1f388edee removes stale duplicate external-mirror chops from the checks lane. Reviewed intervening commits and fast-forwarded integrated base 67d846327; its new mirrored-issue close path already uses settle_closed_task_bead_gates after commit/publish and outside the store lock, so it correctly consumes this epic with no extra change. Verification on integrated HEAD: 113 focused task-gate/config/external-mirror tests passed; just check passed every lint, validation, and selected-test gate. Follow-up outcomes: sase-k0.1 stale core floor was duplicate sase-jj and causally recorded on sase-jx.5; the floor ratchet landed in 688eec2bd and sase-jj is now closed done. sase-k0.2 stale sase-js Symvision entries were duplicate sase-kc; commit c30bcb012 removed the exemptions and cleaned or wired the symbols, and sase-kc is closed done. sase-k0.3 proposed none. Nested epic sase-k0.4 is now closed done after triaging its one proposal: exact flake tasks sase-jq and sase-kd received corroboration, closed sase-iu was not reopened for historical record bookkeeping, active epic sase-j7 received the outcome, and no new task was warranted. All descendants are closed and the original epic contract is complete.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-k0.1](sase-k0.1.md) | Shared pending bead-gate lookup | ✓ closed | small | 2026-08-12 | 1 | 1 |
| [sase-k0.2](sase-k0.2.md) | Make the reconciler converge on gates it no longer tracks | ✓ closed | medium | 2026-08-12 | 1 | 1 |
| [sase-k0.3](sase-k0.3.md) | Settle bead gates from sase bead close | ✓ closed | medium | 2026-08-12 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-k0: Converge task bead gates and settle them the moment a bead closes [closed]"]
    n1["sase-k0.1: Shared pending bead-gate lookup [closed]"]
    n2["sase-k0.2: Make the reconciler converge on gates it no longer tracks [closed]"]
    n3["sase-k0.3: Settle bead gates from sase bead close [closed]"]
    n4["sase-k0.4: Finish and land task bead gate convergence [closed]"]
    n5["sase-k0.4.1: Complete the promised convergence regression coverage [closed]"]
    n6["sase-k0.4.2: Verify and close epic sase-k0 [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n4 --> n5
    n4 --> n6
    n1 -.-> n2
    n1 -.-> n3
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k0.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.1/README.md) | [sase-k0.1](sase-k0.1.md) | 1 |
| [bbugyi200.athena.sase-k0.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.2/README.md) | [sase-k0.2](sase-k0.2.md) | 1 |
| [bbugyi200.athena.sase-k0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.3/README.md) | [sase-k0.3](sase-k0.3.md) | 1 |
| [bbugyi200.athena.sase-k0.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.4.1/README.md) | [sase-k0.4.1](sase-k0.4.1.md) | 1 |
| [bbugyi200.athena.sase-k0.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.4.2/README.md) | [sase-k0.4.2](sase-k0.4.2.md) | 1 |
| [bbugyi200.athena.sase-k0.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.4.land/README.md) | [sase-k0.4](sase-k0.4.md) | 1 |
| [bbugyi200.athena.sase-k0.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.land/README.md) | [sase-k0](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`07f050d`](https://github.com/sase-org/sase/commit/07f050d3a28091a0b7ef28a4e7ca1502e7ec3398) | refactor(bead): share pending gate lookup | [sase-k0.1](sase-k0.1.md) | 2026-08-12 11:35:07 EDT |
| sase | [`875f67b`](https://github.com/sase-org/sase/commit/875f67b74da1e3829b9b2ec72be40df8e9be6726) | feat(bead): settle pending gates immediately on task bead close | [sase-k0.3](sase-k0.3.md) | 2026-08-12 12:11:34 EDT |
| sase | [`95a9b45`](https://github.com/sase-org/sase/commit/95a9b457502c898d74c448219eec417e6800cd11) | fix(axe): sweep stale bead task gates | [sase-k0.2](sase-k0.2.md) | 2026-08-12 12:30:24 EDT |
| sase | [`9960d74`](https://github.com/sase-org/sase/commit/9960d7444062db28ce0bf8ee08011ace31272407) | test: cover task triage project-state convergence | [sase-k0.4.1](sase-k0.4.1.md) | 2026-08-12 13:11:21 EDT |
| sase | [`1f388ed`](https://github.com/sase-org/sase/commit/1f388edee0000664e053a153f8c3a708d2c9545c) | fix(axe): remove duplicate external-mirror lumberjack chop entries | [sase-k0.4.2](sase-k0.4.2.md) | 2026-08-12 14:27:40 EDT |
| sase--plans | [`sase--plans@8ace23b`](https://github.com/sase-org/sase--plans/commit/8ace23b5914b9fc4ce0407b46fc555cfcbc5759f) | docs(plans): mark task gate convergence epics done | [sase-k0.4](sase-k0.4.md) | 2026-08-12 14:58:54 EDT |

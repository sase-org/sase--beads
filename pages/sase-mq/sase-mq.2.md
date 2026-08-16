# Bead: sase-mq.2 — Durable operational workspace leases

[Bead Pages](../README.md) / [sase-mq](README.md) / sase-mq.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.035](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.035.md) · **Assignee:** `sase-mq.2` · **Size:** medium
**Created:** 2026-08-15 23:39:03 EDT · **Closed:** 2026-08-16 01:29:01 EDT
**Plan:** [202608/primary\_workspace\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/primary_workspace_ownership.md)

## Description

operation-leases: add reusable claimed-workspace lifecycle support for synchronous jobs, monitors, and detached procs.

## Notes

[2026-08-16T05:21:42Z · sase-mq.2] Implemented operational workspace leases: sase-core workspace_lease ownership decisions (no primary/reserved numbers, settlement policy kind, named failure messages) plus Python sase.workspace_provider.lease (sync context manager + submit_leased_proc_request with preclaim/prepare/transfer). Proc settlement always releases operational-lease policies, including monitor-like rows. Focused tests: 18 passed. Rust workspace_lease: 7 passed. just check lint is green except pre-existing unused public FilesQueryIndexResult. Justfile epic-symbols caused scoped-test escalation; handing just check-full to a monitor.

[2026-08-16T05:29:01Z · sase-mq.2--1] Operational workspace leases land: sase-core workspace_lease ownership decisions (no primary/reserved numbers, settlement policy kind, named failure messages) plus Python sase.workspace_provider.lease (sync context manager + submit_leased_proc_request with preclaim/prepare/transfer). Proc settlement always releases operational-lease policies, including monitor-like rows. Verified: 18 lease + 22 ownership + 43 proc service/facade tests passed; Rust workspace_lease 7 passed. just check-full lint green except pre-existing unused public FilesQueryIndexResult (sase-mq.1 already noted). No primary fallback; legacy #1 and reserved #2-#9 rejected.

[2026-08-16T05:29:56Z · sase-mq.2--1] Verified operational leases: lease+ownership 40 passed, proc settlement 43 passed, Rust workspace_lease 7 passed; just check-full failed only on pre-existing unused FilesQueryIndexResult (sase-mq.1). Failures never fall back to the user-owned primary; reserved #1-#9 rejected; settlement always releases operational-lease policies.

## Dependencies

- **Depends on:** [sase-mq.1](sase-mq.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mq.3](sase-mq.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mq.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mq.2.md) | [sase-mq.2](sase-mq.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`419c5a9`](https://github.com/sase-org/sase/commit/419c5a9fcdcce70bb42d3ebd22974ced71321163) | feat(workspace): add durable operational workspace leases | [sase-mq.2](sase-mq.2.md) | 2026-08-16 01:31:13 EDT |
| sase-core | [`sase-core@3e6502d`](https://github.com/sase-org/sase-core/commit/3e6502d10db0f404379c587ad8c2928493b0cf4b) | feat(workspace\_lease): add operational lease eligibility and policy kinds | [sase-mq.2](sase-mq.2.md) | 2026-08-16 01:33:59 EDT |

# Bead: sase-1nf.1 — sase-core reaper removes read-only trees and exempts system-service sessions

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.1` · **Size:** medium
**Created:** 2026-10-20 13:36:13 EDT · **Closed:** 2026-10-20 14:22:05 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

reap-core: in sase-core, make managed-tmp removal repair owner write permission inside the candidate tree and retry once, add the system-service ancestry exemption to the launch-scratch liveness observer, and surface the blocking process in dead-launch and pressure skip reasons.

## Notes

[2026-10-20T18:22:05Z · sase-1nf.1] sase-core managed-tmp removal now repairs owner u+wx (O_DIRECTORY|O_NOFOLLOW fchmod) inside the candidate tree and retries once on PermissionDenied; 0555 vault trees are removed with bytes counted, a symlink to an outside 0555 dir is not followed or chmod'd, bucket 0500 file removal still fails, and a dead-launch nested 0555 tree is removed. Launch-scratch liveness exempts sshd-like system-service ancestry (counted in additive exempted_system_service, serde default 0) and fails closed for sudo/same-uid/orphan/user.slice/missing status/pid-reuse/cycle; per-pid diagnostics name comm and ppid and are appended (capped) to dead-launch and pressure skip reasons. Binding round-trip includes the new field. sase tool run check passed in sase-core (run 9ec26ebae270dea7b7dbf5d28f0e47bf).

## Dependencies

- **Blocks:** [sase-1nf.2](sase-1nf.2.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.1/README.md) | [sase-1nf.1](sase-1nf.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6f354df`](https://github.com/sase-org/sase-core/commit/6f354df4d9650777087c06cc937526d95671d493) | fix(managed-tmp): repair 0555 trees and exempt system-service sessions | [sase-1nf.1](sase-1nf.1.md) | 2026-10-20 14:23:21 EDT |

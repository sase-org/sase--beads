# Bead: sase-m9.2.1.2 — One detached proc service and supervisor

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.2` · **Size:** medium
**Created:** 2026-08-15 06:14:48 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

unified-proc-supervisor: introduce one typed Python proc submission request and service over the new Rust lifecycle, then promote the monitor bootstrap/supervision guarantees into the proc kernel: double-fork/reparenting, bounded acknowledgement and launch barrier, scrubbed child environment, boot-aware supervisor identity, direct persisted argv execution, merged binary-safe output, total and idle timeouts, process-group TERM-to-KILL escalation, stop intent, and reboot/pid-reuse/loss reconciliation. Move through settling and make settlement resumable and idempotent so the command, output, result envelope, workspace claim, artifacts, and follow-up policy are durable before terminal state. Keep Proc.log_path authoritative and only prune store-owned logs below the proc log root. Migrate ordinary proc CLI/API callers to the service, retaining compatibility reconciliation for already-running legacy rows and removing the weaker supervisor only after focused crash-boundary tests pass.

## Dependencies

- **Depends on:** [sase-m9.2.1.1](sase-m9.2.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.3](sase-m9.2.1.3.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.4](sase-m9.2.1.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.2/README.md) | [sase-m9.2.1.2](sase-m9.2.1.2.md) | 0 |

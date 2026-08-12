# Bead: sase-jz.3 — Roll the new ci\_watch out to the live host and verify

[Bead Pages](../README.md) / [sase-jz](README.md) / sase-jz.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yi](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yi/README.md) · **Assignee:** `sase-jz.3` · **Size:** small
**Created:** 2026-08-12 10:39:07 EDT
**Plan:** [202608/retire\_audit\_chops\_and\_gate\_ci\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_audit_chops_and_gate_ci_fixes.md)

## Description

rollout: bump the package version, push bugyi-chops, drop the now-inert `wait_runners: 0` from the `ci_watch` lane, reinstall the plugin from git, and verify with a dry run plus a live tick that the gate path files exactly one gate and no duplicates.

## Dependencies

- **Depends on:** [sase-jz.2](sase-jz.2.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-jz.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-jz.3/README.md) | [sase-jz.3](sase-jz.3.md) | 0 |

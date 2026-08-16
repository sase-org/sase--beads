# Bead: sase-m9.3.1.3 — Migrate remaining durable ACE producers

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.3` · **Size:** large
**Created:** 2026-08-15 15:17:19 EDT · **Closed:** 2026-08-15 18:52:08 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

migrate-bead-plugin-and-utility-producers: migrate bead and artifact mutations, notification actions, monitor control, AXE background commands, and plugin/update operations to explicit domain argv plus durable request/result files; classify prompt stashing and other short UI-only work as ordinary threaded Textual workers with no proc row, and remove all remaining duck-typed callable submission paths while keeping sensitive payloads out of argv and logs.

## Notes

[2026-08-15T22:52:08Z · sase-m9.3.1.3] Implemented approved ACE producer migration; verified focused regressions, app-title startup test, proc producer inventory, just fmt, and just check with the scoped lane escalated to the full suite.

## Dependencies

- **Depends on:** [sase-m9.3.1.1](sase-m9.3.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.4](sase-m9.3.1.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.1.3.md) | [sase-m9.3.1.3](sase-m9.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7d7581a`](https://github.com/sase-org/sase/commit/7d7581a21cc7e3418979f09b2b17c8ec0daba0f6) | feat(ace): migrate remaining durable producers | [sase-m9.3.1.3](sase-m9.3.1.3.md) | 2026-08-15 18:56:54 EDT |

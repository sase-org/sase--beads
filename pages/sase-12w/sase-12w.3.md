# Bead: sase-12w.3 — TUI handoff returns after authentication

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.3` · **Size:** medium
**Created:** 2026-09-18 08:50:40 EDT · **Closed:** 2026-09-18 12:30:43 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

tui: make the ACE sudo terminal handoff pass --detach, handle the new execution_started payload, toast the background handoff, and surface the executing state on the sudo gate and its finalize proc.

## Notes

[2026-09-18T16:30:43Z · sase-12w.3] Implemented detached sudo TUI handoff/executing projection; verified focused sudo TUI/gate-panel/completion tests, just fix, just check, and epic-symbols clear.

## Dependencies

- **Depends on:** [sase-12w.2](sase-12w.2.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.5](sase-12w.5.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.3/README.md) | [sase-12w.3](sase-12w.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e98ef5b`](https://github.com/sase-org/sase/commit/e98ef5b1ce3c5fdb70db2890fa1ec0dd79b77478) | feat(tui): detach sudo handoff execution | [sase-12w.3](sase-12w.3.md) | 2026-09-18 12:32:40 EDT |

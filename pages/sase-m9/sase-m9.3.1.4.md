# Bead: sase-m9.3.1.4 — Read-only ACE proc observation

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.4` · **Size:** large
**Created:** 2026-08-15 15:17:29 EDT · **Closed:** 2026-08-15 21:04:00 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

readonly-ace-proc-observer: replace ProcQueue ownership and ProcMirror writes with an off-event-loop, read-only observer of supervisor-owned proc ids, results, active counts, and logs; marshal selective/coalesced updates through the UI thread, restore authoritative state after ACE restart, preserve Procs-pane and optimistic completion behavior, and prove quitting or killing ACE cannot affect active commands.

## Notes

[2026-08-16T01:04:00Z · sase-m9.3.1.4] Implemented the read-only ACE proc observer migration. Verified focused observer/procs/lifecycle/plugin/query suites, repaired failure cluster, and non-test just check gates; full-suite just check escalated and failed twice with different non-repeatable tests that passed in isolation under concurrent workspace load.

## Dependencies

- **Depends on:** [sase-m9.3.1.2](sase-m9.3.1.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m9.3.1.3](sase-m9.3.1.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.5](sase-m9.3.1.5.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.1.4.md) | [sase-m9.3.1.4](sase-m9.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c48404`](https://github.com/sase-org/sase/commit/8c48404581cabc8b49f1534ef4e64f542363141d) | feat(ace): observe durable procs read-only | [sase-m9.3.1.4](sase-m9.3.1.4.md) | 2026-08-15 21:06:05 EDT |

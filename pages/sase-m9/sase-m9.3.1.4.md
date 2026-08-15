# Bead: sase-m9.3.1.4 — Read-only ACE proc observation

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.4` · **Size:** large
**Created:** 2026-08-15 15:17:29 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

readonly-ace-proc-observer: replace ProcQueue ownership and ProcMirror writes with an off-event-loop, read-only observer of supervisor-owned proc ids, results, active counts, and logs; marshal selective/coalesced updates through the UI thread, restore authoritative state after ACE restart, preserve Procs-pane and optimistic completion behavior, and prove quitting or killing ACE cannot affect active commands.

## Dependencies

- **Depends on:** [sase-m9.3.1.2](sase-m9.3.1.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-m9.3.1.3](sase-m9.3.1.3.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.5](sase-m9.3.1.5.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3.1.4/README.md) | [sase-m9.3.1.4](sase-m9.3.1.4.md) | 0 |

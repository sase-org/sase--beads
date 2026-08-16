# Bead: sase-m9.3.1.5 — Detached-option retirement and invariants

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.5` · **Size:** large
**Created:** 2026-08-15 15:17:38 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

detach-retirement-and-enforcement: remove public -d/--detached from proc run, proc list, and the legacy task alias because every new proc is supervisor-owned; keep --session only for attribution, always include unattributed procs alongside an explicit session filter, retain hidden legacy-kind history filtering, add the one-release suppressed obsolete-token diagnostic, update help/completions/docs, and enforce statically and in tests that proc APIs accept only durable argv and no active proc is owned by the ACE pid.

## Dependencies

- **Depends on:** [sase-m9.3.1.4](sase-m9.3.1.4.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3.1.5/README.md) | [sase-m9.3.1.5](sase-m9.3.1.5.md) | 0 |

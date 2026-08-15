# Bead: sase-m9.2.1.3 — Named proc-shell addressing and CLI

[Bead Pages](../README.md) / [sase-m9.2.1](sase-m9.2.1.md) / sase-m9.2.1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.md) · **Assignee:** `sase-m9.2.1.3` · **Size:** small
**Created:** 2026-08-15 06:14:55 EDT
**Plan:** [202608/unified\_proc\_shell\_platform\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_proc_shell_platform_1.md)

## Description

named-proc-shell-cli: add -N/--shell to proc run and list, resolve show/kill references by exact fully qualified shell name before exact id and unique id prefix, and derive bare names beneath the calling sase agent. Validate names against slash, proc-id ambiguity, invalid agent components, and malformed qualification; map each shell name to its distinct namespaced concurrency key without conflating the fields; scope active uniqueness by project and allow reuse only after settlement. Update filtering, JSON and rich renderers, help, completions, and tests using “named proc shell” language while preserving historical name visibility and avoiding a top-level sase shell command.

## Dependencies

- **Depends on:** [sase-m9.2.1.2](sase-m9.2.1.2.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.2.1.4](sase-m9.2.1.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.3/README.md) | [sase-m9.2.1.3](sase-m9.2.1.3.md) | 0 |

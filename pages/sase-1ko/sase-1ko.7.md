# Bead: sase-1ko.7 — Claude root bundle via system-prompt file, helper bundle, exact-path native exclusion

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.7` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

claude: create the `claude_explicit_instructions` sunset flag. When it is on, deliver the root bundle with `--append-system-prompt-file` and the helper bundle with `--append-subagent-system-prompt-file`. Exclude SASE-owned root and home instruction files by exact path, and turn auto-memory off per decision. Flag off restores E1's after-state exactly.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.7/README.md) | [sase-1ko.7](sase-1ko.7.md) | 0 |

# Bead: sase-11i.5 — Visual snapshots and cross-surface parity

[Bead Pages](../README.md) / [sase-11i](README.md) / sase-11i.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lq.md) · **Assignee:** `sase-11i.5` · **Size:** medium
**Created:** 2026-09-15 21:08:42 EDT · **Closed:** 2026-09-16 00:14:38 EDT
**Plan:** [202609/xprompt\_keyword\_arg\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/xprompt_keyword_arg_highlighting.md)

## Description

visual-parity: pin the new rendering with dark and light PNG snapshots, prove the TUI and LSP classify the same text identically, and confirm the CLI and pager surfaces render every new role.

## Notes

[2026-09-16T04:13:54Z · sase-11i.5] PROPOSED FOLLOW-UP: visual suite baseline drift - full `just test-visual` in this workspace failed broadly with 600 unrelated PNG mismatches while the new xprompt argument snapshots passed targeted compare; investigate renderer/golden baseline drift separately.

[2026-09-16T04:14:38Z · sase-11i.5] Implemented and verified xprompt argument visual parity: focused parity/CLI tests passed; targeted argument PNG snapshots passed update and compare; reviewed dark/light PNGs; just check passed. Full just test-visual was attempted and failed broadly with unrelated renderer/golden drift, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-11i.2](sase-11i.2.md) ✓ · ⧖ 2026-09-15
- **Depends on:** [sase-11i.4](sase-11i.4.md) ✓ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.5/README.md) | [sase-11i.5](sase-11i.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`649be3c`](https://github.com/sase-org/sase/commit/649be3cb27d016bab20e2323dd9a646482428aa6) | test(xprompt): pin argument highlight parity | [sase-11i.5](sase-11i.5.md) | 2026-09-16 00:16:31 EDT |

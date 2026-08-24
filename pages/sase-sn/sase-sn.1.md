# Bead: sase-sn.1 — Canonical text-block closing rule in the Python scanners

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.1` · **Size:** medium
**Created:** 2026-08-24 06:11:47 EDT · **Closed:** 2026-08-24 07:04:46 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

grammar: close a `[[...]]` text block at the first `]]` in argument-terminator position instead of the first `]]` anywhere, and apply that rule to all three Python argument scanners.

## Notes

[2026-08-24T11:04:46Z · sase-sn.1] Implemented the canonical Python [[...]] text-block terminator helper across argument matching, argument splitting, and alt-inspector splitting; verified focused pytest parser/directive/alt/chop coverage and a passing just check; epic-symbols empty.

## Dependencies

- **Blocks:** [sase-sn.4](sase-sn.4.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sn.5](sase-sn.5.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sn.6](sase-sn.6.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sn.1/README.md) | [sase-sn.1](sase-sn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6ca6e79`](https://github.com/sase-org/sase/commit/6ca6e798ed2277eab8e1741abc66b2117480f455) | fix(xprompt): honor text-block terminators in python scanners | [sase-sn.1](sase-sn.1.md) | 2026-08-24 07:06:02 EDT |

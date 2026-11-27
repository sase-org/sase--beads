# Bead: sase-1vd.6 — Telegram copy buttons

[Bead Pages](../README.md) / [sase-1vd](README.md) / sase-1vd.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.6` · **Size:** small
**Created:** 2026-11-26 10:49:29 EST · **Closed:** 2026-11-26 13:11:06 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

## Description

telegram-copy: render declared snippets on live Telegram question messages as CopyTextButton rows, and list long or out-of-prose values in the message text so Telegram shows every declared value.

## Notes

[2026-11-26T18:11:06Z · sase-1vd.6] Implemented Telegram CopyTextButton rows with compact label packing, rendered long and out-of-prose snippets in an escaped Copyable section, and added compatibility and formatting tests. Verified with sase tool run check (exit 0; lint, mypy, and 889 tests passed) and confirmed no remaining epic symbols.

## Dependencies

- **Depends on:** [sase-1vd.1](sase-1vd.1.md) ✓ · ⧖ 2026-11-26
- **Blocks:** [sase-1vd.7](sase-1vd.7.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.6/README.md) | [sase-1vd.6](sase-1vd.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@c99da27`](https://github.com/sase-org/sase-telegram/commit/c99da27247cf4d1625827f5e31f7978163d31bf3) | feat(questions): add Telegram copy buttons | [sase-1vd.6](sase-1vd.6.md) | 2026-11-26 13:12:10 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vd.6][1] | Need the phase scope, design file, decisions, and prior notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.6/README.md

<!-- sase:referenced-by:end -->

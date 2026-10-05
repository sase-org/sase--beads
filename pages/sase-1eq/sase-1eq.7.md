# Bead: sase-1eq.7 — sase-telegram cutover

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.7` · **Size:** small
**Created:** 2026-10-02 06:51:29 EDT · **Closed:** 2026-10-03 13:44:55 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

telegram: switch sase-telegram to a new-first compatibility import helper and the raw_prompt.md artifact. Rename the bot command to /macros, keeping a flag-gated /xprompts alias, and rename its internals and docs.

## Notes

[2026-10-03T17:44:55Z · sase-1eq.7] Telegram cutover done in sase-telegram checkout (uncommitted working tree): new src/sase_telegram/macro_compat.py resolves 13 sase.macro names new-first with sase.xprompt fallback; xprompt_commands.py -> macro_commands.py with /macros command and macros strings; /xprompts kept as unlisted flag-gated alias (legacy_xprompt_syntax, missing flag counts as enabled); retry reads raw_prompt.md then raw_xprompt.md; README + docs/inbound.md updated; CHANGELOG/sdd untouched. Verified: sase tool run check run 619f471f9337f976a02908139491255c succeeded (ruff clean, mypy 49 files clean, 737 passed); epic-symbols reports no --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1eq.10](sase-1eq.10.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.4](sase-1eq.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.7/README.md) | [sase-1eq.7](sase-1eq.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-telegram | [`sase-telegram@d335fb8`](https://github.com/sase-org/sase-telegram/commit/d335fb8f9dfa5f0b534b3fdbbc591e505e7b5947) | refactor(telegram): rename xprompt surface to macros with compat alias | [sase-1eq.7](sase-1eq.7.md) | 2026-10-03 13:46:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.7/README.md

<!-- sase:referenced-by:end -->

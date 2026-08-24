# Bead: sase-sn.4 — Narrow the \`+\`-to-space decoding to bare colon arguments

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.4` · **Size:** small
**Created:** 2026-08-24 06:11:48 EDT · **Closed:** 2026-08-24 08:04:26 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

decode: apply the `+` space substitution only on the whitespace-delimited bare colon argument form, so `C++` in prose, quoted values, and text blocks stop being corrupted.

## Notes

[2026-08-24T12:04:26Z · sase-sn.4] Narrowed + decoding to the bare unquoted colon form. decode_xprompt_arg_value's + substitution now applies only where the plan specifies (bare #name:a,b colon args); removed the blanket decode from parse_args (paren/comma grammar) and from parse_workflow_reference's paren-rest, colon shorthand, and backtick-colon branches, plus the matching call sites in _parsing_references.parse_arguments, processor._consume_trailing_shorthand_text and its colon_arg backtick branch, _xprompt_swarm_parsing, and workflow_executor_steps_embedded_types. Verified: parse_args/parse_workflow_reference paren and backtick/shorthand-text forms preserve literal + (C++, Application+Support); bare colon form still decodes + to space; updated tests/test_xprompt_parsing.py and tests/test_xprompt_processor_args.py to match, added tests/test_directives_wait.py::test_wait_bead_keyword_does_not_decode_plus_to_space and swapped the now-stale two+words whitespace-rejection parametrize case for a literal two words case. just check passed clean (lint gates + scoped tests). sase bead epic-symbols sase-sn.4 reports no entries.

## Dependencies

- **Depends on:** [sase-sn.1](sase-sn.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sn.5](sase-sn.5.md) ◐ · ⧖ 2026-08-24
- **Blocks:** [sase-sn.6](sase-sn.6.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sn.4/README.md) | [sase-sn.4](sase-sn.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec76ec6`](https://github.com/sase-org/sase/commit/ec76ec6ef9e0ea99d1f89a96d2edbaa64372e844) | fix(xprompt): narrow +-to-space decoding to bare colon arguments | [sase-sn.4](sase-sn.4.md) | 2026-08-24 08:05:19 EDT |

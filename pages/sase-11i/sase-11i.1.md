# Bead: sase-11i.1 — Argument span grammar in the Rust core

[Bead Pages](../README.md) / [sase-11i](README.md) / sase-11i.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lq.md) · **Assignee:** `sase-11i.1` · **Size:** medium
**Created:** 2026-09-15 21:08:38 EDT · **Closed:** 2026-09-15 21:40:19 EDT
**Plan:** [202609/xprompt\_keyword\_arg\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/xprompt_keyword_arg_highlighting.md)

## Description

core-spans: add a frontend-neutral xprompt/directive argument span tokenizer to sase-core that decomposes every argument form into key, assign, value, and delimiter roles with literal-type and validity classification, and stop treating unresolvable values as type mismatches.

## Notes

[2026-09-16T01:40:19Z · sase-11i.1] Implemented core xprompt/directive argument span grammar and PyO3 binding; verified cargo fmt, focused cargo tests for argument_spans/xprompt_args/unresolvable diagnostics/PyO3 compile, sase bead epic-symbols sase-11i.1, and LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check.

## Dependencies

- **Blocks:** [sase-11i.2](sase-11i.2.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11i.4](sase-11i.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.1/README.md) | [sase-11i.1](sase-11i.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4c25db2`](https://github.com/sase-org/sase-core/commit/4c25db2f59c9dbb18638bacdb2e288665485b105) | feat: add xprompt argument span grammar | [sase-11i.1](sase-11i.1.md) | 2026-09-15 21:41:21 EDT |

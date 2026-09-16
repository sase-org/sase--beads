# Bead: sase-11i.6.1 — Complete incremental argument spans and remove suffix reparsing

[Bead Pages](../README.md) / [sase-11i.6](sase-11i.6.md) / sase-11i.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11i.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11i.land.md) · **Assignee:** `sase-11i.6.1` · **Size:** medium
**Created:** 2026-09-16 00:36:13 EDT · **Closed:** 2026-09-16 01:00:47 EDT
**Plan:** [202609/finish\_argument\_highlighting.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_argument_highlighting.md)

## Description

core-editing: preserve structural spans in unfinished calls and make directive extraction use bounded shared parsing.

## Notes

[2026-09-16T05:00:47Z · sase-11i.6.1] Implemented open parenthesized argument parsing, exact-offset directive parsing, shared comma boundaries, and open directive validity gating in sase-core. Verified cargo test -p sase_core editor::xprompt_args::tests --lib; cargo test -p sase_core editor::argument_spans::tests --lib; cargo test -p sase_core_py xprompt_argument_spans_binding_returns_open_structural_spans --lib; debug timing medians for mixed %queue/#foo workload 5.049ms/100 lines, 32.819ms/600, 54.891ms/1000; and env PYO3_PYTHON=/home/bryan/.local/bin/python3.14 LD_LIBRARY_PATH=/home/bryan/.local/share/uv/python/cpython-3.14.7-linux-x86_64-gnu/lib just check passed. epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-11i.6.2](sase-11i.6.2.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11i.6.3](sase-11i.6.3.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11i.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11i.6.1/README.md) | [sase-11i.6.1](sase-11i.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@874077c`](https://github.com/sase-org/sase-core/commit/874077cf7f4d6cd8982b8e62925a11e9bdd63075) | fix(editor): preserve open argument spans | [sase-11i.6.1](sase-11i.6.1.md) | 2026-09-16 01:02:10 EDT |

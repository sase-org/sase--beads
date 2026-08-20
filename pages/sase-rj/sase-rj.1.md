# Bead: sase-rj.1 — Canonical directive completion contract in sase-core

[Bead Pages](../README.md) / [sase-rj](README.md) / sase-rj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08s](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08s.md) · **Assignee:** `sase-rj.1` · **Size:** medium
**Created:** 2026-08-20 13:44:19 EDT · **Closed:** 2026-08-20 14:17:37 EDT
**Plan:** [202608/xprompt\_directive\_completion\_parity.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_directive_completion_parity.md)

## Description

directive-contract: define the complete directive and argument schema, grammar-aware cursor context, value-provider roles, and Python bindings in sase-core so frontends no longer maintain divergent hard-coded catalogs.

## Notes

[2026-08-20T18:17:37Z · sase-rj.1] Verified the canonical directive completion contract in sase-core: audited names/aliases/syntax/keywords (including %wait bead= and %xprompts_enabled), grammar-aware classifier (colon vs paren, keyword-value clauses, selected/conflict suppression, quotes/text-blocks, UTF-16), static+dynamic candidate builders (bead ranking, kind-filtered identity targets), sase_core_rs JSON bindings, and just check (fmt, clippy -D warnings, full workspace tests including LSP wait/bead= order).

[2026-08-20T18:19:31Z · sase-rj.1] Verified canonical directive catalog, grammar-aware classifier, static/dynamic candidate builders, and Python JSON bindings in sase-core; just check (fmt, clippy -D warnings, workspace tests including LSP wait completion with bead=) passed; no leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-rj.2](sase-rj.2.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rj.3](sase-rj.3.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rj.1/README.md) | [sase-rj.1](sase-rj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@04c27f2`](https://github.com/sase-org/sase-core/commit/04c27f2a22a9d1e621b6acec666789a3fb89395e) | feat(editor): add canonical xprompt directive completion contract | [sase-rj.1](sase-rj.1.md) | 2026-08-20 14:20:14 EDT |

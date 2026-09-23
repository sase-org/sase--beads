# Bead: sase-171.3 — Discoverability and bulk-select accelerators

[Bead Pages](../README.md) / [sase-171](README.md) / sase-171.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q6.md) · **Assignee:** `sase-171.3` · **Size:** medium
**Created:** 2026-09-23 11:58:17 EDT · **Closed:** 2026-09-23 15:18:33 EDT
**Plan:** [202609/updates\_tab\_agent\_cli\_install.md](https://github.com/sase-org/sase--plans/blob/main/202609/updates_tab_agent_cli_install.md)

## Description

discover-bulk: add the Available scope, the `*` mark-all-like-this key, a cross-scope hint when a filter matches nothing, the final detail call-to-action, docs, and goldens.

## Notes

[2026-09-23T19:17:48Z · sase-171.3] PROPOSED FOLLOW-UP: just check is red on unrelated pre-existing breakage — stale --epic-symbol sase-16y(MemberJumpSection) in Justfile (bead closed) fails symvision, and 16 scoped-lane tests fail in tests/test_bead prompt-rendering plus an order-dependent AcePage leak test

[2026-09-23T19:18:33Z · sase-171.3] discover-bulk done: Available scope (4-scope cycle, counts, empty message), asterisk mark-all with section/filter scoping and toasts, cross-scope filter hint, new detail CTA, docs, 13 new unit/widget tests plus 2 new goldens with 27 regenerated-and-verified PNGs; unit suites and visual check clean

## Dependencies

- **Depends on:** [sase-171.2](sase-171.2.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-171.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-171.3/README.md) | [sase-171.3](sase-171.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2f89266`](https://github.com/sase-org/sase/commit/2f892663858debbb0bc0b6befd62ddc11f6cb918) | feat(plugins-browser): add Available scope, mark-all toggle, and cross-scope filter hint | [sase-171.3](sase-171.3.md) | 2026-09-23 15:20:50 EDT |

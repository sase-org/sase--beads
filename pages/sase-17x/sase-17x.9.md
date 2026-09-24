# Bead: sase-17x.9 — Grammar-aware completion popup and signature line

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.9` · **Size:** medium
**Created:** 2026-09-24 11:29:28 EDT · **Closed:** 2026-09-24 15:15:43 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

completion-popup: load the grammar at idle and wire the resolver into the input. This adds token highlighting, advisory diagnostics, the floating fuzzy popup fed by in-memory TUI entities and debounced providers, the zsh menu-select key rules, and the live signature line with its chips.

## Notes

[2026-09-24T17:24:00Z · 0qz--code] symvision_green_master sweep: ensure_command_line_spec and CompletionSpecCacheError stay public under --epic-symbol sase-17x(...) Justfile entries. Your phase consumes them; remove both entries when it lands.

[2026-09-24T19:15:22Z · sase-17x.9] PROPOSED FOLLOW-UP: PNG goldens for popup/signature/diagnostic/indexing states need just fix-tui-screenshots generation and inspection

[2026-09-24T19:15:43Z · sase-17x.9] completion-popup landed: grammar idle-load, sync resolve overlay, fuzzy popup (in-memory + debounced providers), menu-select keys, live signature/chips. Verified: 49 passed +1 env-skip in tests/ace/tui/command_line/, 3 pilot tests green, ruff check+format clean, symvision demanded and got the 2 entry removals (gate red before and after on sibling in-flight surface only)

## Dependencies

- **Blocks:** [sase-17x.10](sase-17x.10.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.11](sase-17x.11.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.5](sase-17x.5.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.7](sase-17x.7.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.9/README.md) | [sase-17x.9](sase-17x.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d4dc96e`](https://github.com/sase-org/sase/commit/d4dc96eb4a163f33c73d2e6a93c3731a227b2829) | feat(ace-tui): add command-line completion popup phase sase-17x.9 | [sase-17x.9](sase-17x.9.md) | 2026-09-24 15:17:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0qz--code][1] | verify 17x.9 open before adding epic-symbol entries | 1 |
| read-by | [agent:sase-17x.9][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qz.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.9/README.md

<!-- sase:referenced-by:end -->

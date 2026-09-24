# Bead: sase-17x.9 — Grammar-aware completion popup and signature line

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.9` · **Size:** medium
**Created:** 2026-09-24 11:29:28 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

completion-popup: load the grammar at idle and wire the resolver into the input. This adds token highlighting, advisory diagnostics, the floating fuzzy popup fed by in-memory TUI entities and debounced providers, the zsh menu-select key rules, and the live signature line with its chips.

## Notes

[2026-09-24T17:24:00Z · 0qz--code] symvision_green_master sweep: ensure_command_line_spec and CompletionSpecCacheError stay public under --epic-symbol sase-17x(...) Justfile entries. Your phase consumes them; remove both entries when it lands.

## Dependencies

- **Blocks:** [sase-17x.10](sase-17x.10.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.11](sase-17x.11.md) ◐ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.5](sase-17x.5.md) ✓ · ⧖ 2026-09-24
- **Depends on:** [sase-17x.7](sase-17x.7.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.9/README.md) | [sase-17x.9](sase-17x.9.md) | 0 |

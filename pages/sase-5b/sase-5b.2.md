# Bead: sase-5b.2 — Phase 2 — Inline short-term memory into \`AGENTS.md\`

[Bead Pages](../README.md) / [sase-5b](README.md) / sase-5b.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5b.2`
**Created:** 2026-06-26 19:51:45 UTC · **Closed:** 2026-06-26 20:45:55 UTC
**Plan:** [202606/inline\_short\_term\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202606/inline_short_term_memory.md)

## Notes

COMMIT: 7ecd0292e

[2026-07-27T21:37:47Z · sase-a1.land] [2026-06-26T20:43:55Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 complete: short-term memory is inlined into managed + minimal AGENTS.md.

Code:
- src/sase/amd/_memory.py: _render_managed_agents inlines short notes via inline_memory_section (replaces _short_memory_references bullets); plan_amd_memory_sync takes generated_short_notes overlay + validates short-note structure (blockers on missing H1 / H4+).
- src/sase/main/init_memory/roots.py: threads the FRESH generated memory/sase.md body into both the managed render and the minimal AGENTS.md (single-pass idempotency, Gotcha #2); _minimal_agents_content inlines sase.md (no @).
- src/sase/memory/inventory.py: short notes treated as reachable explicitly (Gotcha #3); inlined short notes reported loaded in build_memory_inventory (status only, no double-counted stats).
- src/sase/amd/_agents_doc.py: _short_memory_paths recognizes inlined '### memory/<f>.md (Title)' headers (legacy '- @memory' bullets still recognized for migration).
- Removed dead MINIMAL_AGENTS_CONTENT constant; dropped now-used Phase-1 epic-symbols (validate_short_memory_structure, inline_memory_section) from Justfile _lint-pyvision.
Provider shims untouched (still @AGENTS.md) — that is Phase 3.

Tests/lint/mypy/pyvision: green. Full 'just test' green (14298 passed).

CAVEAT for Phase 3/4: plan Gotcha #7 is wrong — 'just check' DOES gate on 'sase validate' (init --check). After the renderer change, validate reports expected drift: committed AGENTS.md and the user's chezmoi-home ~/.local/share/chezmoi/home/AGENTS.md need regeneration to the inlined format. NOT regenerated here (regeneration = Phase 4 / sase-5b.4; use_chezmoi=True so 'sase memory init' would deploy to the live home). This is the only 'just check' step that is red.

## Dependencies

- **Depends on:** [sase-5b.1](sase-5b.1.md) ✓
- **Blocks:** [sase-5b.3](sase-5b.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5b.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5b.2/README.md) | [sase-5b.2](sase-5b.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`41de8f1`](https://github.com/sase-org/sase/commit/41de8f1b3ee20673802a4a6817a65bb354f3a3ba) | feat(memory): inline short-term memory into \`AGENTS.md\` (sase-5b.2) | [sase-5b.2](sase-5b.2.md) | 2026-06-26 20:47:21 |

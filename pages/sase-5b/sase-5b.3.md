# Bead: sase-5b.3 — Phase 3 — Provider files become full, identical copies of \`AGENTS.md\`

[Bead Pages](../README.md) / [sase-5b](README.md) / sase-5b.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5b.3`
**Created:** 2026-06-26 19:52:12 UTC · **Closed:** 2026-06-26 21:08:52 UTC
**Plan:** [202606/inline\_short\_term\_memory.md](https://github.com/sase-org/sase--plans/blob/main/202606/inline_short_term_memory.md)

## Notes

COMMIT: 1932a170f

[2026-07-27T21:37:51Z · sase-a1.land] [2026-06-26T21:07:01Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Provider files (CLAUDE/GEMINI/QWEN/OPENCODE) now byte-for-byte copy the root's final AGENTS.md instead of @AGENTS.md shims; chezmoi switched to static CLAUDE.md with .tmpl legacy cleanup; legacy @-shim recognition retained for clean migration. Threaded agents_content through provider_shim_specs/plan (_shared.py), added _final_agents_content in roots.py, and the AMD inventory now classifies full copies as exact_shim. ruff+mypy clean; full 'just test' green (14298 passed). The 'sase validate'/init --check freshness gate is red as expected (regenerate AGENTS.md + provider files) and is deferred to Phase 4 (sase-5b.4) per Gotcha #7. Changes left uncommitted in the working tree.

## Dependencies

- **Depends on:** [sase-5b.2](sase-5b.2.md) ✓
- **Blocks:** [sase-5b.4](sase-5b.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-5b.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-5b.3/README.md) | [sase-5b.3](sase-5b.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`394f41b`](https://github.com/sase-org/sase/commit/394f41b878b8010ee69b68b8f2caf37ee6d198c2) | feat(memory): provider files become full copies of \`AGENTS.md\` (sase-5b.3) | [sase-5b.3](sase-5b.3.md) | 2026-06-26 21:09:42 |

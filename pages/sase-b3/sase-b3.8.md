# Bead: sase-b3.8 — Ctrl+R finder on the shared matcher

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.8

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.8` · **Size:** small
**Created:** 2026-07-30 08:18:43 UTC · **Closed:** 2026-07-30 10:09:05 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

finder: replace the duplicate Python fuzzy scorer in recursive_file_finder with the shared core matcher and the shared highlight helper so both surfaces rank and highlight identically.

## Notes

[2026-07-30T10:09:05Z · sase-b3.8] Implemented shared core fuzzy matcher facade for Ctrl+R finder and shared highlight rendering. Verified: just install; pytest finder/widget/rendering focus (48 passed); pytest -m visual finder snapshot (1 passed); just test-visual (392 passed, 1 skipped). just check passes fmt/ruff/mypy/etc. but fails on unrelated existing symvision private-import findings in clipboard palette modules.

## Dependencies

- **Depends on:** [sase-b3.7](sase-b3.7.md) ✓
- **Blocks:** [sase-b3.9](sase-b3.9.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b3.8/README.md) | [sase-b3.8](sase-b3.8.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`835536a`](https://github.com/sase-org/sase/commit/835536a846a55f596fa707145ca629a5bb46188f) | refactor(tui): reuse shared fuzzy matcher in finder | [sase-b3.8](sase-b3.8.md) | 2026-07-30 10:10:44 |

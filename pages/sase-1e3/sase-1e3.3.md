# Bead: sase-1e3.3 — Narration script contract, deterministic normalizer, lexicon, lint, and guide

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.3` · **Size:** medium
**Created:** 2026-10-01 14:42:44 EDT · **Closed:** 2026-10-01 15:18:51 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

script: implement the narration-script v1 model and parser and the markdown-it AST normalizer with an omissions report and golden fixtures. Add the pronunciation lexicon, `lint` (including the --source number-fidelity check), and the packaged authoring guide behind `guide`.

## Notes

[2026-10-01T19:18:51Z · sase-1e3.3] Script phase done in gh:sase-org/sase-listen (uncommitted): model/parser/cleaner, markdown-it normalizer with omissions, lexicon apply+sha256, lint with structural/residue/warning ids plus --source fidelity, guide with brief swap, 3 golden fixtures, docs pages. Verified: sase tool run check green (ruff, format, mypy strict, codespell, 55 pytest incl 41 new), every fixture output lints with zero errors, epic-symbols clean. One minimal cross-phase touch: tests/test_cli.py stub assertions updated for implemented lint/script (render stub unchanged); no pyproject/uv.lock/nav/other-phase edits.

## Dependencies

- **Depends on:** [sase-1e3.1](sase-1e3.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.6](sase-1e3.6.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.3/README.md) | [sase-1e3.3](sase-1e3.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |
| read-by | [agent:sase-1e3.3][3] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.3/README.md

<!-- sase:referenced-by:end -->

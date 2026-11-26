# Bead: sase-1vd.1 — Core copy contract and creation-time validation

[Bead Pages](../README.md) / [sase-1vd](README.md) / sase-1vd.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1gp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1gp.md) · **Assignee:** `sase-1vd.1` · **Size:** medium
**Created:** 2026-11-26 10:49:28 EST · **Closed:** 2026-11-26 12:41:33 EST
**Plan:** [202611/question\_copy\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202611/question_copy_panel.md)

## Description

copy-contract: add the strict and tolerant `copy` normalizers, wire types, and PyO3 bindings to sase-core, then route `sase questions` and question-gate creation through them in sase while read paths stay tolerant.

## Notes

[2026-11-26T17:41:33Z · sase-1vd.1] Implemented strict Rust question-copy normalization and tolerant display parsing, wired creation/gate validation through the Rust-backed facade, added coverage and binding checks, keyed display exports to consuming phase sase-1vd.3, and verified focused tests, Symvision, and successful  (ToolRun 5a174ee852ae42ff6bf6b5439cf73276).

## Dependencies

- **Blocks:** [sase-1vd.3](sase-1vd.3.md) ◐ · ⧖ 2026-11-26
- **Blocks:** [sase-1vd.6](sase-1vd.6.md) ✓ · ⧖ 2026-11-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vd.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.1/README.md) | [sase-1vd.1](sase-1vd.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@76638b5`](https://github.com/sase-org/sase-core/commit/76638b579e7e937ae1d18ef677fc61ccbe5da8c0) | feat(questions): add question copy contracts | [sase-1vd.1](sase-1vd.1.md) | 2026-11-26 12:42:49 EST |
| sase | [`b9964f3`](https://github.com/sase-org/sase/commit/b9964f31a8ec7c5f68217fb1dbd4904089c3337f) | feat(questions): validate and display copy metadata | [sase-1vd.1](sase-1vd.1.md) | 2026-11-26 12:43:57 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vd.1][1] | Need the phase scope, notes, decisions, and design file before completing the assigned work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vd.1/README.md

<!-- sase:referenced-by:end -->

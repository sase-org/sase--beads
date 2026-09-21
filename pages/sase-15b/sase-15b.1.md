# Bead: sase-15b.1 — Split crates/sase\_core/src/bead/cli.rs

[Bead Pages](../README.md) / [sase-15b](README.md) / sase-15b.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.1` · **Size:** medium
**Created:** 2026-09-21 11:31:37 EDT · **Closed:** 2026-09-21 13:43:41 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

## Description

bead_cli: decompose the 4,276-line bead CLI module into dispatch, per-command handler, argument parsing, and rendering submodules under bead/cli/.

## Notes

[2026-09-21T17:43:41Z · sase-15b.1] Split bead/cli.rs (4276 lines) into bead/cli/ tree, just check green, 47/47 cli tests pass, largest new file 584 lines

## Dependencies

- **Blocks:** [sase-15b.2](sase-15b.2.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.1/README.md) | [sase-15b.1](sase-15b.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@61dc4e1`](https://github.com/sase-org/sase-core/commit/61dc4e19713189e8e9d0a2e3aeedafcf16d584ad) | refactor(bead): split bead cli.rs into bead/cli module tree | [sase-15b.1](sase-15b.1.md) | 2026-09-21 13:46:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability (split epic phase evidence) | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md

<!-- sase:referenced-by:end -->

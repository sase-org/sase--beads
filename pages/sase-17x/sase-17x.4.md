# Bead: sase-17x.4 — Command-line proc tag and retention bucket

[Bead Pages](../README.md) / [sase-17x](README.md) / sase-17x.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qs](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qs.md) · **Assignee:** `sase-17x.4` · **Size:** small
**Created:** 2026-09-24 11:29:22 EDT · **Closed:** 2026-09-24 11:53:34 EDT
**Plan:** [202609/command\_line\_panel.md](https://github.com/sase-org/sase--plans/blob/main/202609/command_line_panel.md)

## Description

proc-retention: in sase-core, give finished procs tagged `command-line` their own retention bucket of 50 so they never evict operational proc history. Export the tag and limit through the binding and move sase's sase-core revision pin.

## Notes

[2026-09-24T15:53:11Z · sase-17x.4] PROPOSED FOLLOW-UP: commit+push the sase-core command-line retention change in the linked sase-core checkout and move sase-core-revision.txt past it (agents cannot commit, so the pin still points at eef7ca4)

[2026-09-24T15:53:34Z · sase-17x.4] sase-core: COMMAND_LINE_PROC_TAG=command-line + LIMIT=50 with own retention bucket in apply_retention (named-service precedence kept); 2 new store tests + binding getters pass via just test -p sase_core/sase_core_py. sase: src/sase/procs/command_line.py re-export, tag test, config/docs bucket notes; ruff/fmt/mypy/keep-sorted clean. Pin move left as follow-up (no agent commits).

## Dependencies

- **Blocks:** [sase-17x.5](sase-17x.5.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17x.6](sase-17x.6.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17x.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.4/README.md) | [sase-17x.4](sase-17x.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f6e17fb`](https://github.com/sase-org/sase/commit/f6e17fb2c9adfbc82c4c1c726867b9026a512450) | feat(sase-17x.4): command-line proc tag and retention bucket in sase | [sase-17x.4](sase-17x.4.md) | 2026-09-24 12:05:27 EDT |
| sase-core | [`sase-core@f405c44`](https://github.com/sase-org/sase-core/commit/f405c440a048595c7d9572e23b5dacfcf887050c) | feat(procs): command-line proc tag retention bucket in Rust store | [sase-17x.4](sase-17x.4.md) | 2026-09-24 12:10:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17x.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17x.4/README.md

<!-- sase:referenced-by:end -->

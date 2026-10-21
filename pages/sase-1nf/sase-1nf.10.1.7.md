# Bead: sase-1nf.10.1.7 — Repair verified stale explicit manifest entries

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.7` · **Size:** medium
**Created:** 2026-10-20 15:40:52 EDT · **Closed:** 2026-10-20 20:04:55 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

## Description

manifest-repair: extend explicit local-owner manifest repair to verified stale file lists, retain corrupt-candidate diagnostics, and prove idempotence and owner isolation.

## Notes

[2026-10-21T00:04:36Z · sase-1nf.10.1.7--2] PROPOSED FOLLOW-UP: Remove five stale Symvision --epic-symbol entries for closed phase sase-1nf.10.1.3 from Justfile — primary check run 163435dab024b0fd6b919c2a4d633cfb fails only on these entries, Justfile is identical to HEAD, and parent epic notes #1/#2 already record independent base-identical reproductions (no separate task bead found).

[2026-10-21T00:04:55Z · sase-1nf.10.1.7--2] Completed verified stale manifest-list repair, corruption diagnostics, owner isolation, documentation, and idempotence coverage. Focused repair tests passed (15); sase-core check passed (ToolRun 44a17b6a9b17827f40e1b18c93ef8159). Primary check reached all earlier stages and failed only on five stale epic-symbol entries for closed sibling phase sase-1nf.10.1.3 in unchanged Justfile; recorded as a proposed follow-up. No symbols remain for this phase.

## Dependencies

- **Depends on:** [sase-1nf.10.1.1](sase-1nf.10.1.1.md) ✓ · ⧖ 2026-10-20
- **Blocks:** [sase-1nf.10.1.8](sase-1nf.10.1.8.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.7.md) | [sase-1nf.10.1.7](sase-1nf.10.1.7.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@cfae073`](https://github.com/sase-org/sase-core/commit/cfae07381f846808ab7708e108456d1fea0fba5c) | feat(vcs): expose verified manifest repair policy | [sase-1nf.10.1.7](sase-1nf.10.1.7.md) | 2026-10-20 20:05:42 EDT |
| sase | [`b6a7a58`](https://github.com/sase-org/sase/commit/b6a7a58fdd0afb34310f6786d6e2ebfa310cf3e1) | feat(agents-sync): repair verified stale manifest lists | [sase-1nf.10.1.7](sase-1nf.10.1.7.md) | 2026-10-20 20:10:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.10.1.1][1] | Need later-phase consumers so unused facade APIs can be epic-symbol keyed to still-open beads | 1 |
| read-by | [agent:sase-1nf.10.1.7--2][2] | Verify final phase notes before closing the completed manifest-repair work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.10.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.7.md

<!-- sase:referenced-by:end -->

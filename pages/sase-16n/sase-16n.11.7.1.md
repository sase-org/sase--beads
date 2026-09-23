# Bead: sase-16n.11.7.1 — sase-core macOS test fix, accept line-join fix, and tag cleanups

[Bead Pages](../README.md) / [sase-16n.11.7](sase-16n.11.7.md) / sase-16n.11.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16n.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16n.11.land.md) · **Assignee:** `sase-16n.11.7.1` · **Size:** medium
**Created:** 2026-09-23 14:10:52 EDT · **Closed:** 2026-09-23 14:33:06 EDT
**Plan:** [202609/project\_tags\_landing\_gaps\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/project_tags_landing_gaps_finish.md)

## Description

core-accept: make the case-variant collision test pass on case-insensitive file systems; accept removal no longer deletes the newline after a line-end ref and counts refs hidden inside a rejected glued match; pre-v5 LSP catalogs fall back to enabled rows for accept; fix stale comments and dead checks.

## Notes

[2026-09-23T18:33:06Z · sase-16n.11.7.1] core-accept done in sase-core: accept deletion ends at ref (group 1) so end-of-line refs keep newlines, orphan collapse is horizontal-ws only with lone-line removal, glued-match rejection resumes at next byte; pre-v5 LSP catalogs fall back to entry-derived targets; macOS case-variant test builds records directly; removed dead sibling check, const-derived catalog bound, deleted test-only builder (no py/binding callers). Verified: focused project_tag (25), collision (3), vcs_project (15), LSP vcs_completion (16 incl. new fallback test) green; sase tool run check succeeded (35 ok suites, 0 failures; one transient lib failure on first gate run passed standalone and on full re-run). No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-16n.11.7.3](sase-16n.11.7.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16n.11.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.1/README.md) | [sase-16n.11.7.1](sase-16n.11.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@fb1ca29`](https://github.com/sase-org/sase-core/commit/fb1ca29f50310ff5dc45f7cf3d3dc9431e3d4a97) | fix(core): project-tag accept line-join, macOS test, and tag cleanups | [sase-16n.11.7.1](sase-16n.11.7.1.md) | 2026-09-23 14:34:32 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16n.11.7.1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-16y.land][2] | child scope for red-test triage | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16n.11.7.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16y.land/README.md

<!-- sase:referenced-by:end -->

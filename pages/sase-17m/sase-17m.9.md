# Bead: sase-17m.9 — Pin bump and agents sidecar session pages

[Bead Pages](../README.md) / [sase-17m](README.md) / sase-17m.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qh](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0qh.md) · **Assignee:** `sase-17m.9` · **Size:** medium
**Created:** 2026-09-23 22:46:42 EDT · **Closed:** 2026-09-25 18:04:05 EDT
**Plan:** [202609/agent\_session\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_rename.md)

## Description

session-pages: bump the core pin and the Python schema mirrors. Publish agents-sidecar pages under sessions/, keep permanent redirect stubs at the old families/ paths for historical commit-footer links, and update the sidecar docs, templates, and goldens.

## Notes

[2026-09-25T22:03:42Z · sase-17m.9--4] PROPOSED FOLLOW-UP: just _lint-symvision fails on HEAD 938d2d8fe — `_OwnerRecordLookup` in src/sase/bead/cli_work_cleanup_targets.py is imported by src/sase/bead/cli_work_cleanup_selection.py. Already recorded on in-progress epic sase-19o as DISCOVERED ISSUE; sase-17d.12.2 renamed the Protocol in another workspace.

[2026-09-25T22:04:05Z · sase-17m.9--4] Pinned sase-core 2a0fc2ab and bumped Python schema mirrors; published agents-sidecar pages under sessions/ with permanent families/ redirect stubs; updated sidecar docs, templates, goldens, and hosted-link generation. Verified with 368 agents_sync/sdd tests and 237 core/hold/fleet tests. just check still fails on HEAD-only _OwnerRecordLookup private-import lint from 938d2d8fe (sase-19o DISCOVERED ISSUE).

## Dependencies

- **Blocks:** [sase-17m.10](sase-17m.10.md) ✓ · ⧖ 2026-09-23
- **Depends on:** [sase-17m.8](sase-17m.8.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.9.md) | [sase-17m.9](sase-17m.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7cb8359`](https://github.com/sase-org/sase/commit/7cb8359534d90a04aa09d012bc4c6b2190cb2ce9) | feat(agents-sync): publish sidecar session pages and bump core pin | [sase-17m.9](sase-17m.9.md) | 2026-09-25 19:04:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.2k.cld][1] | Audit: confirm the core flip landed before the sase-side mirror bump, causing the schema-mismatch outage | 1 |
| read-by | [agent:research.2k.final][2] | Verify the incident's core-flip/pin-bump phase ordering for the consolidated research report | 1 |
| read-by | [agent:sase-17m.9--4][3] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2k.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.2k.final/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17m.9.md

<!-- sase:referenced-by:end -->

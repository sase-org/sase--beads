# Bead: sase-tj.3 — The agents query profile

[Bead Pages](../README.md) / [sase-tj](README.md) / sase-tj.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0da](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0da.md) · **Assignee:** `sase-tj.3` · **Size:** medium
**Created:** 2026-08-25 08:09:39 EDT · **Closed:** 2026-08-25 09:51:43 EDT
**Plan:** [202608/artifacts\_agents\_pane.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_agents_pane.md)

## Description

dialect: author agents_query_schema(), register it as a built-in pane profile, and add cross-language query goldens and conformance coverage.

## Notes

[2026-08-25T13:02:24Z · sase-tj.3] PROPOSED FOLLOW-UP: Add deferred v2 agent query fields - effort needs an effort/model_effort column; bead needs bead_id; epic needs epic_id or parent_bead_id; workspace needs workspace_id/path; xprompts needs xprompt names/directive metadata; patch stays deferred until the catalog phase reports cl_name/meta_patch cardinality.

[2026-08-25T13:51:43Z · sase-tj.3] Implemented agents query schema/profile registration and agents conformance goldens; recorded deferred v2 field note; verified focused profile/conformance pytest passed, sidecar retry regression test passed, just check passed, and epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-tj.1](sase-tj.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tj.4](sase-tj.4.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tj.8](sase-tj.8.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tj.3/README.md) | [sase-tj.3](sase-tj.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`70a9d10`](https://github.com/sase-org/sase/commit/70a9d101583f0610a48ae09fe304c97b6d0ff232) | feat(query-profile): add agents built-in profile | [sase-tj.3](sase-tj.3.md) | 2026-08-25 09:53:04 EDT |

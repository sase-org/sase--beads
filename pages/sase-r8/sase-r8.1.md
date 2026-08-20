# Bead: sase-r8.1 — Tracked sidecar home for link truth

[Bead Pages](../README.md) / [sase-r8](README.md) / sase-r8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08f.md) · **Assignee:** `sase-r8.1` · **Size:** small
**Created:** 2026-08-19 19:16:35 EDT · **Closed:** 2026-08-19 19:59:41 EDT
**Plan:** [202608/artifact\_link\_graph.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_graph.md)

## Description

home: stop writing the Referenced By index under .sase/, put it in a tracked links/ tree, and start committing it.

## Notes

[2026-08-19T23:59:41Z · sase-r8.1] Referenced By structured truth now lives at sidecar/links/<artifact-relpath>.json (v1, original extension preserved, no provider prefix). git_exclude.py unchanged: SASE_GIT_INFO_EXCLUDE_PATTERNS still ignore .sase/ and /sase/repos/ but not links/. commit_sdd_files includes the JSON in HEAD. sase doctor project.referenced_by_index errors when a committed unfenced Referenced By block has no links/ JSON in HEAD and ignores fenced design-doc examples. just check passed. Backfilled and pushed the one live projection (plans/links/202608/monitor_followup_wait_release.md.json); the other three research-era hits are fenced examples, not managed blocks.

[2026-08-20T00:00:59Z · sase-r8.1] Referenced By structured truth now lives at sidecar/links/<artifact-relpath>.json (v1, original extension preserved, no provider prefix). git_exclude.py unchanged: SASE_GIT_INFO_EXCLUDE_PATTERNS still ignore .sase/ and /sase/repos/ but not links/. commit_sdd_files includes the JSON in HEAD. sase doctor project.referenced_by_index errors when a committed unfenced Referenced By block has no links/ JSON in HEAD and ignores fenced design-doc examples. just check passed. Backfilled and pushed the one live projection (plans/links/202608/monitor_followup_wait_release.md.json); the other three research-era hits are fenced examples, not managed blocks.

[2026-08-20T00:07:27Z · sase-r8.1] Referenced By structured truth lives at sidecar/links/<artifact-relpath>.json; doctor project.referenced_by_index covers missing committed indexes; live plans sidecar backfill already pushed. Agents-repo .sase-v2-stage-hbkbmy5o/ is unrelated sase-qt staging and was not committed.

## Dependencies

- **Blocks:** [sase-r8.3](sase-r8.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-r8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-r8.1/README.md) | [sase-r8.1](sase-r8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f3992a`](https://github.com/sase-org/sase/commit/0f3992a03caef10fb3a7e6dd930efa39969de481) | fix(sdd): commit Referenced By index under tracked links/ | [sase-r8.1](sase-r8.1.md) | 2026-08-19 20:01:49 EDT |

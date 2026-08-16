# Bead: sase-m6.7.1.1 — Relations and grouping become declared contract facts

[Bead Pages](../README.md) / [sase-m6.7.1](sase-m6.7.1.md) / sase-m6.7.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.7.md) · **Assignee:** `sase-m6.7.1.1` · **Size:** medium
**Created:** 2026-08-16 02:53:14 EDT · **Closed:** 2026-08-16 03:14:45 EDT
**Plan:** [202608/artifacts\_relations\_and\_grouping.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_relations_and_grouping.md)

## Description

vocabulary: replace the PaneRelationDecl/PaneGroupingDecl placeholders with real records, derive RELATIONS and GROUPING from named rules, add the additive ref.relations and ref.grouping declaration blocks, and surface both in the pane explainer.

## Notes

[2026-08-16T07:13:58Z · sase-m6.7.1.1] PROPOSED FOLLOW-UP: Remove stale Symvision epic-symbol allowlist entry — just check fails in _lint-symvision because Justfile still passes --epic-symbol sase-mq.5(mark_sidecar_sync_hint), but bead sase-mq.5 is closed.

[2026-08-16T07:14:45Z · sase-m6.7.1.1] Verified just fmt, focused pytest for contract compiler/synthetic provider/pane CLI/sidecar config (86 passed), and .venv/bin/sase artifact pane show patches --json reports schema 2 with RELATIONS/GROUPING ON and Patch relations ancestors/children/siblings. just check was run and failed in unrelated Symvision stale epic-symbol allowlist entry for closed bead sase-mq.5(mark_sidecar_sync_hint); recorded PROPOSED FOLLOW-UP on this phase bead.

[2026-08-16T07:16:30Z · sase-m6.7.1.1] Verified focused pytest lane passed, pane CLI schema 2 reports Patch relations and grouping, git diff --check was clean; just check was blocked only by unrelated stale Symvision allowlist for closed bead sase-mq.5.

## Dependencies

- **Blocks:** [sase-m6.7.1.2](sase-m6.7.1.2.md) ◐ · ⧖ 2026-08-16
- **Blocks:** [sase-m6.7.1.5](sase-m6.7.1.5.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.7.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.7.1.1/README.md) | [sase-m6.7.1.1](sase-m6.7.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2abe188`](https://github.com/sase-org/sase/commit/2abe188aae089950b13f22b9c5c299baaf5e6cef) | feat(artifacts): declare pane relation and grouping facts | [sase-m6.7.1.1](sase-m6.7.1.1.md) | 2026-08-16 03:17:40 EDT |

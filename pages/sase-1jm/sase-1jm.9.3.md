# Bead: sase-1jm.9.3 — Archive chooser sections, container restore, and copy keys

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.3` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT · **Closed:** 2026-10-12 19:01:54 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

archive-chooser-copy: add the READ section, open the chooser on container rows with Restore clan, keep marked restore reachable, gate Fork on a retained chat, hydrate off the event loop, add the dedicated agents_copy_reference y action, fix the doubled %l prefix, make %j copy the bundle JSON, update help and docs, and capture chooser goldens.

## Notes

[2026-10-12T22:26:19Z · sase-1jm.9.3--1] Verified archive-chooser-copy: READ section (Open chat / y / %); container Enter Restore clan|session; marks Restore N even when cursor unrestorable; Fork gated on retained chat; off-loop hydrate via _archive_run_off_thread/_archive_spawn; agents_copy_reference y; %l format_markdown_link without doubled agent:; %j bundle JSON off-thread; help Copy Mode and docs; chooser goldens inspected (agents_archive_chooser_120x40 Restore to inbox, agents_archive_chooser_marked_120x40 Restore 2 marked); visual report applied created=2 skipped=0; epic-symbols clean. Preparing just check for host close.

[2026-10-12T23:01:38Z · sase-1jm.9.3--2] PROPOSED FOLLOW-UP: test_neighbors_map_shows_dismissed_revive_cells asserts revive in jump-panel prefix text but production shows ▶ archive (jump_opens_archive=yes) — identical on clean HEAD c4d84f9a1a; same leftover as KNOWN test_dismissed_marker; previously noted on sase-1jx.13.5 with no task bead

[2026-10-12T23:01:54Z · sase-1jm.9.3--2] Verified archive-chooser-copy: READ section (Open chat / y / %); container Enter Restore clan|session (l/h still expand/collapse); marks Restore N even when cursor unrestorable/unreadable; Fork gated on retained chat; off-loop hydrate via _archive_run_off_thread/_archive_spawn; agents_copy_reference y tab-disjoint from artifacts_copy_reference; %l format_markdown_link without doubled agent:; %j bundle JSON off-thread (Inbox metadata JSON); help Copy Mode lists %! %l %j %d y; docs in docs/ace.md and docs/configuration.md; footer restore chip unchanged. Chooser goldens inspected: visual report applied created=2 skipped=0 (agents_archive_chooser_120x40 Restore to inbox; agents_archive_chooser_marked_120x40 Restore 2 marked; ARCHIVE+READ headings, Open chat/Copy/More copy). 52 phase unit tests passed. sase bead epic-symbols clean. sase tool run check c0fe2ba749f88adc38ec1224335470b7: 1 NEW that reproduces identically on clean HEAD (test_neighbors_map_shows_dismissed_revive_cells — PROPOSED FOLLOW-UP, same leftover as KNOWN test_dismissed_marker) plus 10 KNOWN (sase-1ic import budget; sase-1k4 Project: fake/tmp header tests; remaining KNOWN include node-finder, archive parking/reader, source-groups, path-label exemption).

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.5](sase-1jm.9.5.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.3.md) | [sase-1jm.9.3](sase-1jm.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9fa4792`](https://github.com/sase-org/sase/commit/9fa479245cd17a709d4358896b55c74d166b34ac) | feat(ace): add Archive chooser READ section, container restore, and copy keys | [sase-1jm.9.3](sase-1jm.9.3.md) | 2026-10-12 19:03:24 EDT |

# Bead: sase-uk.5 — A press that always lands

[Bead Pages](../README.md) / [sase-uk](README.md) / sase-uk.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ej](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ej.md) · **Assignee:** `sase-uk.5` · **Size:** medium
**Created:** 2026-08-26 17:44:38 EDT · **Closed:** 2026-08-26 21:19:57 EDT
**Plan:** [202608/link\_traversing\_pager.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_traversing_pager.md)

## Description

follow: define the `resolve_ref` interface with its CLI-backed implementation, open resolved targets as new pager documents rather than escaping to a viewer, remember and dim dead ends, delegate media to `graphics`, and add the one-shot `y`/`E` prefixes.

## Notes

[2026-08-27T01:14:54Z · sase-uk.5] PROPOSED FOLLOW-UP: target_resolution_ref() cannot build a valid commit: ref for DIFF-origin bare short-sha tokens (commit refs require <repo>@<sha>, and the scanner has no repo context) — those links paint but a press toasts "nothing to follow/edit/copy" instead of resolving. No adapter emits PagerOrigin.DIFF documents yet, so this is latent until the diff/cli scanning adapter lands; that adapter will need to either attach typed commit targets itself or extend target_resolution_ref with repo context.

[2026-08-27T01:15:18Z · sase-uk.5] PROPOSED FOLLOW-UP: resolve.py._bead_link_target() builds its document via resolve_show_batch()/build_show_batch_document() but deliberately skips the detail_enricher=_with_artifact_link_neighborhood step that `sase bead show --format full` uses, because that enricher calls sys.exit(1) on failure (unsafe inside a keypress handler). So a bead reached by following a link in the pager shows a slightly less enriched LINKS section than opening the same bead directly via `sase bead show`. Fixing this needs a non-exiting variant of the enricher.

[2026-08-27T01:19:57Z · sase-uk.5] Auto-closed by `sase stitch create` after create_commit landed 699037f21 ("feat(pager): add link resolution and follow/copy/edit actions"). No verification is implied by this note. Reopen with `sase bead open sase-uk.5`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-uk.4](sase-uk.4.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-uk.6](sase-uk.6.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uk.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uk.5/README.md) | [sase-uk.5](sase-uk.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`699037f`](https://github.com/sase-org/sase/commit/699037f215b69128b8e49a5ccd7a2c588b002c27) | feat(pager): add link resolution and follow/copy/edit actions | [sase-uk.5](sase-uk.5.md) | 2026-08-26 21:19:08 EDT |

# Bead: sase-1ck.10 — Remove the beta flag and finish docs

[Bead Pages](../README.md) / [sase-1ck](README.md) / sase-1ck.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tv](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tv.md) · **Assignee:** `sase-1ck.10` · **Size:** medium
**Created:** 2026-09-29 08:13:48 EDT · **Closed:** 2026-09-29 23:26:53 EDT
**Plan:** [202609/bead\_note\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_note_attachments.md)

## Description

ga: delete the flag's Off branches and close the flag bead. Finish user docs, help, and skill sources, run the end-to-end acceptance sweep, and record the follow-up proposals, including the memory update.

## Notes

[2026-09-30T02:36:20Z · sase-1ck.10] PROPOSED FOLLOW-UP: same-text @attachment reuse rejected — note with @./shot.png plus @attachment:shot.png fails core one-to-one manifest validation (tokens [shot.png x2] vs manifest [shot.png]); reproduces on pristine base binary with flag on; suspect sase-core validate_note_attachment_manifest multiset comparison vs the grammar same-text reuse rule -r Recording pre-existing defect found in ga sweep

[2026-09-30T02:40:20Z · sase-1ck.10] PROPOSED FOLLOW-UP: show -i cells crashes on TTY with multi-attachment bead — pager attached-target span exceeds body length (span 16767:16777 vs body ~4360, bead:tmp-1); reproduces on clean base tree in tmux PTY with flag on; piped show degrades fine; suspect show_images cell-thumbnail span accounting -r Recording pre-existing defect found in ga sweep

[2026-09-30T02:53:07Z · sase-1ck.10] PROPOSED FOLLOW-UP (root-caused): show crashes with styled TTY output — attachment_targets_for_body str.find runs on the SGR-containing raw body (chip at raw 751:761) but PagerSection validates against Text.from_ansi plain (chip at 411:421, len 582); any SGR before a chip breaks it. Thumbnails mask it by lengthening plain. Triggered when images resolve to never on a color TTY (e.g. SASE_AGENT=1 forces never; also -i never or bead.show.images=never with attachments). Fix: search Text.from_ansi(body).plain in _show_batch_sections. -r Root cause for styled-show crash found in ga sweep

[2026-09-30T02:55:42Z · sase-1ck.10] PROPOSED FOLLOW-UP (expanded): same styled-show crash also blocks kitty mode on a real kitty terminal — kitty mode renders text previews only in the pager body (pixels emit outside it), so plain stays short and validation fails identically (span 753:763 vs 585 on tmp-2). Only cells mode with enough thumbnail rows masks it. True kitty-pixel end-to-end shots are blocked on this fix. -r Kitty mode also blocked by styled-show crash

[2026-09-30T02:56:14Z · sase-1ck.10] PROPOSED FOLLOW-UP: memory update — sase_beads.md Notes And History and memory-sase-beads.template.md should mention @path attachments, @@, and sase bead attach -r Ga follow-up from epic plan

[2026-09-30T02:56:25Z · sase-1ck.10] PROPOSED FOLLOW-UP: attachments in bead descriptions and sase bead create (-d/-f values) -r Ga follow-up from epic plan

[2026-09-30T02:56:36Z · sase-1ck.10] PROPOSED FOLLOW-UP: @attachment:<bead>/<name> prompt expansion and cross-bead reuse -r Ga follow-up from epic plan

[2026-09-30T02:56:47Z · sase-1ck.10] PROPOSED FOLLOW-UP: fold sase artifact create --bead into attachments -r Ga follow-up from epic plan

[2026-09-30T02:56:57Z · sase-1ck.10] PROPOSED FOLLOW-UP: gate/Telegram rendering of attachments and photo delivery -r Ga follow-up from epic plan

[2026-09-30T02:57:08Z · sase-1ck.10] PROPOSED FOLLOW-UP: sase-nvim highlighting of the @path attachment grammar -r Ga follow-up from epic plan

[2026-09-30T02:57:19Z · sase-1ck.10] PROPOSED FOLLOW-UP: iTerm2/sixel preview protocols if a user needs them -r Ga follow-up from epic plan

[2026-09-30T03:01:37Z · sase-1ck.10] PROPOSED FOLLOW-UP: just check _lint-patch-stitch-terminology fails on clean base tree too — 14 defects all in sase-core linked fixture at_bearing_notes.jsonl, none in main repo; verify with just _lint-patch-stitch-terminology on stashed tree (exit 1 identical) -r Pre-existing check failure for ga close

[2026-09-30T03:22:09Z · sase-1ck.10] PROPOSED FOLLOW-UP: test_every_bead_free_text_option_is_classified fails on clean base tree — (attachment, purge, reason) unclassified; lifecycle phase added purge -r without a classification entry -r Pre-existing test failure for ga close

[2026-09-30T03:26:13Z · sase-1ck.10] PROPOSED FOLLOW-UP: just _lint-symvision fails on clean base tree — private import _kitty_graphics_support from doctor.checks_deep_terminal into bead.show_images -r Pre-existing lint failure for ga close

[2026-09-30T03:26:53Z · sase-1ck.10] GA done: flag bead sase-1cl closed with registry/schema/Off-branch removal (attach/note/close/update/+1, fast path, TUI add-note, help texts now unconditional); flag-off tests deleted and flag-on tests unwrapped (83/83 attachment tests pass); docs finished (beads.md Attachments section with tiers/viewing/badges/mixed-fleet, cli.md, configuration keys already present, onboard attach line, sase_new_task skill repro-attach example). Verified: scratch-store acceptance sweep (inline/quoted/roster-reuse/escape round-trip, prose-free attach, 300MiB sparse byte-exact + sparse-preserved, failure atomicity with carets, binary whole-arg hint, piped outputs free of escapes/bytes, cross-home unavailable badge) plus real cells raster screenshot; ruff/mypy/check_feature_flags clean and 2629 affected-suite tests pass. Pre-existing base-tree issues recorded as PROPOSED FOLLOW-UP (same-text reuse validation, styled-show span crash blocking kitty e2e, terminology lint, purge-reason classification test, symvision private import).

## Dependencies

- **Depends on:** [sase-1ck.6](sase-1ck.6.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.7](sase-1ck.7.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.8](sase-1ck.8.md) ✓ · ⧖ 2026-09-29
- **Depends on:** [sase-1ck.9](sase-1ck.9.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ck.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ck.10/README.md) | [sase-1ck.10](sase-1ck.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3da6e3e`](https://github.com/sase-org/sase/commit/3da6e3ebb8b7dcba1f0d583300ad420d5dbc3058) | feat(beads): remove bead\_note\_attachments beta flag, attachments GA | [sase-1ck.10](sase-1ck.10.md) | 2026-09-29 23:29:58 EDT |

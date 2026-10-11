# Bead: sase-1jz.2 — Pin every clock, zone, and hostname the visual fixtures observe

[Bead Pages](../README.md) / [sase-1jz](README.md) / sase-1jz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zp.md) · **Assignee:** `sase-1jz.2` · **Size:** medium
**Created:** 2026-10-11 13:15:14 EDT · **Closed:** 2026-10-11 15:30:55 EDT
**Plan:** [202610/ci\_green\_visual\_lane.md](https://github.com/sase-org/sase--plans/blob/main/202610/ci_green_visual_lane.md)

## Description

clock-seams: make the FINAL and epic-follow fixture epochs zone-explicit, route every pager age through the pinned time-band epoch, pin the memory pane clock, pin the retry harness hostname, and refresh only the goldens those fixes move.

## Notes

[2026-10-11T18:01:04Z · sase-1jz.2--1] PROPOSED FOLLOW-UP: timeband_past_light_120x40 lost the body-top ─ row — after pinning chrome age to 7d, light 120x40 past heading sits at y=93.2 while past_dark_120x40 and past_light_60x30 keep the ─ separator and heading at y=117.6; capture and verify SHA matched (14431b49), so it is stable theme-layout drift, not a flake. Age token 7d is correct.

[2026-10-11T18:40:01Z · sase-1jz.2--2] Fixed the timeband chrome-rule flake that note #1 recorded as PROPOSED FOLLOW-UP. Cause: _update_trail re-showed #pager-chrome-rule after _update_subject hid it, and _update_time_band returned early on a matching signature without restoring the hide. Signature-matching paints now re-sync the rule; trail hide uses the same helper. Unit test test_time_band_signature_match_keeps_chrome_rule_hidden. Applied 11 remaining timeband goldens (rule gone while the band shows). Host-independence --check clean locally and with TZ=UTC: status=clean created=0 updated=0 stale=0 unchanged=62 (runs 6b14d629 and 882e745a).

[2026-10-11T19:30:42Z · sase-1jz.2--2] PROPOSED FOLLOW-UP: just check (tool run c7ae1d5b) reported 3 NEW timeouts under host load1=30-100, plus 3 KNOWN and 1 FLAKY. NEW: test_blocked_render_is_bounded_and_leaves_the_request_queued (30.6s vs 5s bound), test_cwd_nested_inside_lane_workspace_inherits_claim_and_records_root (monitor never finished), test_fakey_agents_respect_cap_and_release_in_fifo_order (slot-3 park timeout). None import pager chrome/time-band. TUI import closure vs merge-base is +0. Close this phase anyway.

[2026-10-11T19:30:55Z · sase-1jz.2--2] Pinned clock/zone/hostname seams for FINAL, pager age, memory pane, and retry hostname; hid the pager chrome rule consistently while the time band is showing (signature-match no longer leaves it visible); refreshed owned goldens; added tui_screenshot.md host-independence rule. Visual --check clean locally and TZ=UTC (62 unchanged). just check had unrelated NEW/KNOWN/FLAKY timeouts under host load.

## Dependencies

- **Blocks:** [sase-1jz.4](sase-1jz.4.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jz.2.md) | [sase-1jz.2](sase-1jz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`40dd537`](https://github.com/sase-org/sase/commit/40dd5371b9538c23302e99af20affe477b60a4af) | fix(pager): pin visual clocks and hide chrome rule with the time band | [sase-1jz.2](sase-1jz.2.md) | 2026-10-11 16:10:43 EDT |

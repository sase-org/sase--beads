# Bead: sase-1mk.9.2 — Resolve the agents JUMP panel golden drift from the clan Enter change

[Bead Pages](../README.md) / [sase-1mk.9](sase-1mk.9.md) / sase-1mk.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1mk.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1mk.land.md) · **Assignee:** `sase-1mk.9.2` · **Size:** medium
**Created:** 2026-10-18 16:48:00 EDT · **Closed:** 2026-10-18 17:31:13 EDT
**Plan:** [202610/ship\_v0\_18\_0\_post\_repair\_reds.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_post_repair_reds.md)

## Description

jump-golden: decide whether the db14df00e6 JUMP title change is intended, then fix the product or update the golden so Full CI visual-test passes.

## Notes

[2026-10-18T21:30:42Z · sase-1mk.9.2] PROPOSED FOLLOW-UP: test_sigterm_leaves_run_running 124 vs 143 under loaded sase tool run check 8639c2fc8bdf82b78be380c36c544641 — already tracked by sase-1fi; passed in isolation in 7.74s

[2026-10-18T21:30:43Z · sase-1mk.9.2] Decision: the JUMP title itself is unchanged. db14df00e6 is intended product: a clan with exactly one Stopped member (here member06 QUESTION; FAILED is Failed, WAITING is Waiting) now shows the Enter footer hint. The mix snapshot drifted because that extra <enter> choose action binding wraps the footer to 3 lines and shifts the layout (~6% pixels). JUMP chrome stays JUMP · CLAN MEMBERS 00-13 with no WAVES suffix and no truncation. Layered JUMP goldens (60/80/120) were unchanged, so the 4 WAVES +… title in the plan snapshot was a mix-up with the layered fixture. Updated agents_jump_panel_collapsed_in_flight_mix_120x40.png. just fix-tui-screenshots --check over jump_panel + clan_panel + clans + modals (Act-on chooser) + group/panel clan collapse + archive_actions + tribe_clan_summaries: 45 unchanged. Host-independence: mix node check-clean twice, TZ=UTC and TZ=America/New_York, no unstable. Newest completed Full CI visual-test is 39155173153 (only this golden). No task bead owned this concurrent-commit drift.

[2026-10-18T21:30:45Z · sase-1mk.9.2] PROPOSED FOLLOW-UP: test_blocked_render_is_bounded_and_leaves_the_request_queued 30.49s vs <5s under the same loaded check — already tracked by sase-xo; passed in isolation in 0.43s

[2026-10-18T21:31:13Z · sase-1mk.9.2] Verified JUMP mix golden: db14df00e6 Enter hint is intended; updated agents_jump_panel_collapsed_in_flight_mix_120x40.png (footer <enter> choose action, JUMP title still JUMP · CLAN MEMBERS 00-13 with no truncated WAVES suffix). Related clan/footer/chooser goldens unchanged (45). Host-independence TZ=UTC and TZ=America/New_York check-clean, no unstable. Full CI 39155173153 visual-test only this golden. sase tool run check 8639c2fc8bdf82b78be380c36c544641: lint/validation passed; two loaded-lane flakes (sase-1fi, sase-xo) passed in isolation. epic-symbols empty.

## Dependencies

- **Blocks:** [sase-1mk.9.6](sase-1mk.9.6.md) ◐ · ⧖ 2026-10-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.9.2/README.md) | [sase-1mk.9.2](sase-1mk.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b68b516`](https://github.com/sase-org/sase/commit/b68b5166ad6c14bf7549d3b42b37bb698eb70db3) | test(tui): update JUMP mix golden for clan Enter footer hint | [sase-1mk.9.2](sase-1mk.9.2.md) | 2026-10-18 17:32:41 EDT |

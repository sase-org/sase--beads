# Bead: sase-y5.9 — Add a read-only Usage view to the Providers home

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.9` · **Size:** medium
**Created:** 2026-09-07 16:09:26 EDT · **Closed:** 2026-09-08 16:09:49 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

providers-usage-ui: Evolve the provider modal into a shared Providers home with Usage and Routing views, cached first paint, durable update observation, all allowance details, discoverable navigation, and keyboard/PNG regression tests.

## Notes

[2026-09-08T20:08:07Z · sase-y5.9] PROPOSED FOLLOW-UP: tests/pager/test_rendered_link_contract.py::test_kitchen_follow_copy_edit_and_media_for_each_supported_action fails consistently (2/2 runs) on an unmodified pager/link-contract tree, unrelated to this phase - the "unavailable" branch asserts a notification message that never arrives. Discovered while running just check for sase-y5.9; not investigated further since it is outside this phase's scope (ACE Providers Usage view).

[2026-09-08T20:08:39Z · sase-y5.9] PROPOSED FOLLOW-UP: sase.llm_provider.usage.presentation.reset_label(..., verbose=True) appends timestamp_label(resets_at, now), which computes "ago" as max(now - timestamp, 0.0) - for a FUTURE reset this always renders a nonsensical "(0s ago)" suffix (e.g. "in 1h (2027-01-15 04:00:00 EST (0s ago))") instead of an absolute time with no relative suffix. Observed while building the Usage view PNG fixtures. Pre-existing in usage-cli (sase-y5.8) shared presentation code; not fixed here to avoid touching another closed phase's tested behavior.

[2026-09-08T20:09:49Z · sase-y5.9] Added read-only ProviderUsageModal (Providers · Usage): cached first-paint from the store, u-triggered durable refresh via submit_usage_refresh with non-blocking attach-on-reopen/close via proc_projection_for scope_conflict, Enter->details focus, Tab focus-cycle (native Screen binding), Esc always closes even mid-update, and 120/80/60-column responsive layout (meter and column stacking breakpoints). Existing Routing modal/bindings untouched. Added discoverability: 'u' binding + footer text in Launch Control, and a keyless command-palette entry (aliases usage/quota/limits/capacity/subscription/providers) wired to a new action_open_provider_usage. Promoted shared label helpers in llm_provider.usage.presentation to public (age/reset/timestamp/duration/applicability/window/provider status labels + provider_style) so CLI and ACE share one domain-derived rendering path; kept usage_meter/provider_attention_style and presentation's window_style private per symvision (single-file use). Verified: just check clean (fmt, ruff, mypy, symvision, toobig, SASE validation, committed plans, scoped/full test lane); 34 new focused unit/interaction tests pass (state loading, pure rendering incl. width tiers, modal lifecycle/keyboard/update-tracking/attach-on-reopen/failure-summary); 3 new PNG goldens at 120x40/80x32/60x32 inspected and accepted; regenerated 23 pre-existing Models-panel PNG goldens whose footer text changed to include the new Usage binding (diffs visually confirmed as footer-text-only). epic-symbols: none for this phase.

## Dependencies

- **Blocks:** [sase-y5.10](sase-y5.10.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-y5.8](sase-y5.8.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.9/README.md) | [sase-y5.9](sase-y5.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65fe412`](https://github.com/sase-org/sase/commit/65fe4124f62acde7394102045c1882df939e71f2) | feat(ace): add Providers · Usage view to Models panel | [sase-y5.9](sase-y5.9.md) | 2026-09-08 16:11:28 EDT |

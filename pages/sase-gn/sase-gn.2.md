# Bead: sase-gn.2 — Notification tab colors from senders and config

[Bead Pages](../README.md) / [sase-gn](README.md) / sase-gn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uh/README.md) · **Assignee:** `sase-gn.2` · **Size:** medium
**Created:** 2026-08-06 19:27:27 EDT · **Closed:** 2026-08-06 20:46:45 EDT
**Plan:** [202608/bead\_snooze\_and\_notification\_indicator.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_snooze_and_notification_indicator.md)

## Description

notif-tab-style: add an optional sender-declared notification color, an ace.notification_tabs config block, and a deterministic resolver that gives every tab a stable accessible color.

## Notes

[2026-08-07T00:55:02Z · sase-gn.2] PROPOSED FOLLOW-UP: docs/notifications.md "Tabs and Ordering" table is stale after sase-gn.1 — it still says a multi-tagged row appears in each matching tag tab and that Muted absorbs snoozed rows, contradicting the single-valued precedence documented later in the same file.

[2026-08-07T00:55:53Z · sase-gn.2] PROPOSED FOLLOW-UP: tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_anchors_pdf_markdown_source_path is order-dependent — it failed once in a full just check run and passes in isolation and on re-run; unrelated to notifications.

[2026-08-07T00:56:11Z · sase-gn.2] PROPOSED FOLLOW-UP: sender-declared notification colors will not round-trip through the store until sase-core-rs >= the release carrying core commit 97d8925 is published and pinned in pyproject.toml — the published 0.18.4 binding drops the unknown color field on rewrite.

[2026-08-07T00:56:43Z · sase-gn.2] CORRECTION to the previous note: sender colors DO round-trip through the published 0.18.4 binding (verified: the color survives append_notification and load_notifications). The only gap is the aggregated NotificationTabWire.color on the snapshot, which stays None until a sase-core-rs release carrying core commit 97d8925 is pinned in pyproject.toml. The resolver falls through to its built-in/auto-palette rungs until then.

[2026-08-07T00:57:27Z · sase-gn.2] Verification detail: the tab-color path was exercised end to end against a locally built sase_core_rs (append -> classify_notification_tabs -> resolve_notification_tab_color returned the declared #123456 for the beads tab and a stable auto-palette color for an unknown tag). Dev checkouts build the new core automatically; only released-wheel users wait on the pin.

[2026-08-07T01:04:26Z · sase-gn.2] Added an optional sender-declared notification color, an ace.notification_tabs config block, and a deterministic tab-color resolver.

Rust core (committed and pushed as 97d8925 in sase-core): NotificationWire gained an optional color field skipped when absent; the tab pass fills each tab's color from the row with the greatest (activity_at, id) cursor, so the tab wears the color of the row the panel lists first regardless of classification order; malformed values are dropped in the core rather than propagated. Verified with cargo fmt --all --check, cargo clippy --workspace --all-targets -D warnings, and cargo test --workspace, all clean; new crate tests cover newest-wins color selection in both input orders, a resurfaced row outranking a later-sent one, junk rejection, and absence staying off the wire.

Python (committed and pushed as 821966dd2): Notification.color plus wire decoding; validate_color next to validate_icon; presentation.color validated at gate-spec time and applied in _build_notification; color accepted on sase notify create JSON and surfaced through the catalog projection and sase notify show; ace.notification_tabs and ace.notification_indicator_max_counts added to default_config.yml and sase.schema.json; new notification_tab_style resolver reading config through the cached config token, resolving config -> sender -> built-in -> hashed auto-palette, with junk degrading to the next rung instead of raising.

Verified: just check green (every lint gate plus the scoped test lane) on the final rebased tree, after a rust-install rebuild that also cleared a pre-existing binding-scan failure from the concurrently landed snooze phase. 137 notification tests pass against the rebuilt core. Exercised end to end in a live store: append -> classify_notification_tabs -> resolve_notification_tab_color returned the declared #123456 for a colored beads tab and a stable auto-palette color for an unknown tag. New tests pin each precedence rung, the empty-string fallthrough, auto-palette stability and non-collision with built-in defaults, config-key mapping away from __snoozed__/__muted__, invalid-color rejection at gate creation and at notify create, and schema accept/reject cases. The resolver's public symbols are whitelisted in the Justfile against sase-gn.3, which consumes them.

## Dependencies

- **Depends on:** [sase-gn.1](sase-gn.1.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gn.3](sase-gn.3.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.2/README.md) | [sase-gn.2](sase-gn.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@97d8925`](https://github.com/sase-org/sase-core/commit/97d89257d3b905f3076b17f67e92be1a4aa9d965) | feat(notifications): carry a sender-declared color on each notification tab | [sase-gn.2](sase-gn.2.md) | 2026-08-06 20:46:54 EDT |
| sase | [`821966d`](https://github.com/sase-org/sase/commit/821966dd2812965d9deb2cc2045603644e69c342) | feat(ace-tui): give every notification tab a stable, configurable color | [sase-gn.2](sase-gn.2.md) | 2026-08-06 20:49:33 EDT |

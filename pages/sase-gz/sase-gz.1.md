# Bead: sase-gz.1 — Rust core carries a per-tab icon

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.1` · **Size:** medium
**Created:** 2026-08-07 10:28:34 EDT · **Closed:** 2026-08-07 10:44:46 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

core-icon: add `icon` to the core's notification tab record, donated by the newest member row that declares `action_data.panel_icon`, mirroring the existing color-donation rule, with defensive validation and tests; land and release it in sase-core.

## Notes

[2026-08-07T15:12:21Z · sase-gz.1] core-icon landed as sase-core ce8c04b (feat(notifications): donate a per-tab icon from the newest declaring row) and RELEASED AS sase-core-rs 0.19.2 — on PyPI and tagged v0.19.2. The core-floor phase should raise the pyproject floor to >=0.19.2,<0.20.0.

Implementation: NotificationTabWire gained icon: Option<String> (skip_serializing_if = Option::is_none, matching color's convention). TabAccumulator gained icon/icon_cursor; accumulate() now computes the activity cursor once and donates color and icon through a shared donation_wins() newest-cursor helper; ordered_tabs() copies icon through. declared_tab_icon() reads action_data["panel_icon"] defensively — trims, then rejects empty-after-trim, >32 codepoints, >128 bytes, or any control character, matching validate_icon's _MAX_GATE_ICON_CODEPOINTS/_MAX_GATE_ICON_BYTES on the Python side. Donation is not restricted to panel-kind tabs, per the plan.

No sase_core_py change was needed: the binding serializes NotificationTabWire with serde, so classify_notification_tabs() carries the new key automatically.

Verified: 4 new tests in tabs.rs (newest declared icon wins regardless of input order with blank/control/over-long junk ignored; a resurfaced row outranks a newer sent row; any row may donate, not only a panel row; an absent icon stays absent on the wire). cargo fmt --all -- --check clean, cargo clippy --workspace --all-targets -D warnings clean, cargo test --workspace all green (1274 + integration suites, 0 failures). GitHub CI green on the master push and on the release PR (fmt+clippy+test and maturin build + import smoke).

[2026-08-07T15:13:05Z · sase-gz.1] Landed sase-core ce8c04b and released sase-core-rs 0.19.2 (PyPI + tag v0.19.2); tab icon donation with defensive validation and 4 new tests; cargo fmt/clippy/test and GitHub CI all green.

## Dependencies

- **Blocks:** [sase-gz.5](sase-gz.5.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.1/README.md) | [sase-gz.1](sase-gz.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ce8c04b`](https://github.com/sase-org/sase-core/commit/ce8c04ba94ade551e8972f3314935d1130949ecb) | feat(notifications): donate a per-tab icon from the newest declaring row | [sase-gz.1](sase-gz.1.md) | 2026-08-07 10:45:21 EDT |

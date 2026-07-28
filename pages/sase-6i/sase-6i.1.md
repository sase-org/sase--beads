# Bead: sase-6i.1 — Core wire support for icons and the CustomGate action

[Bead Pages](../README.md) / [sase-6i](README.md) / sase-6i.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6i.1`
**Created:** 2026-07-17 03:08:57 UTC
**Plan:** [202607/custom\_notification\_gates.md](https://github.com/sase-org/sase--plans/blob/main/202607/custom_notification_gates.md)

## Description

Phase `rust_wire` in approved epic plan `sase/repos/plans/202607/custom_notification_gates.md`.

## Notes

Implemented rust_wire in sase-core: additive NotificationWire/mobile icon support and round-trips; CustomGate action classification, generic choice/extra/feedback detail projection, neutral response.json/cancellation.json handled state, missing-target and agent-dismissal behavior; updated exports and mobile/gateway contracts. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-6i.2](sase-6i.2.md) ✓

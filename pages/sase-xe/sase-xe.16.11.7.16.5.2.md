# Bead: sase-xe.16.11.7.16.5.2 — Publish the gateway version in fleet hello

[Bead Pages](../README.md) / [sase-xe.16.11.7.16.5](sase-xe.16.11.7.16.5.md) / sase-xe.16.11.7.16.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-xe.16.11.7.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-xe.16.11.7.16.land.md) · **Assignee:** `sase-xe.16.11.7.16.5.2` · **Size:** small
**Created:** 2026-09-15 08:35:19 EDT · **Closed:** 2026-09-15 08:50:33 EDT
**Plan:** [202609/fleet\_ghost\_rows\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_ghost_rows_remaining.md)

## Description

gateway-version-contract: add an honest read-compatible gateway service/version identity to the authenticated hello wire and its contract tests.

## Notes

[2026-09-15T12:50:33Z · sase-xe.16.11.7.16.5.2] Implemented optional gateway_version hello field with service=sase-gateway and package_version from CARGO_PKG_VERSION; updated fleet contract snapshot; verified cargo fmt --all, cargo test -p sase_gateway routes::tests::fleet_enrollment_and_hello_return_identity_and_capabilities -- --exact, cargo test -p sase_gateway contract::tests, just check, and no remaining epic symbols.

## Dependencies

- **Blocks:** [sase-xe.16.11.7.16.5.3](sase-xe.16.11.7.16.5.3.md) ◐ · ⧖ 2026-09-15
- **Blocks:** [sase-xe.16.11.7.16.5.4](sase-xe.16.11.7.16.5.4.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-xe.16.11.7.16.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-xe.16.11.7.16.5.2/README.md) | [sase-xe.16.11.7.16.5.2](sase-xe.16.11.7.16.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@bdb6772`](https://github.com/sase-org/sase-core/commit/bdb67721c223558f48ee7f72696b2541b1b6963e) | feat(gateway): publish hello gateway version | [sase-xe.16.11.7.16.5.2](sase-xe.16.11.7.16.5.2.md) | 2026-09-15 08:52:09 EDT |

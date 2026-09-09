# Bead: sase-xe.16.11.6.1 — Share Fleet request, projection, freshness, and count policy in Rust

[Bead Pages](../README.md) / [sase-xe.16.11.6](sase-xe.16.11.6.md) / sase-xe.16.11.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.11.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.land.md) · **Assignee:** `sase-xe.16.11.6.1` · **Size:** medium
**Created:** 2026-09-09 12:22:08 EDT · **Closed:** 2026-09-09 13:39:23 EDT
**Plan:** [202609/remote\_dispatch\_contract\_and\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_contract_and_acceptance.md)

## Description

core-fleet-contract: add transport-independent typed request and response normalization plus authoritative Fleet and followed-set Focus counting in sase-core, with versioned bindings and regression tests.

## Notes

[2026-09-09T17:38:46Z · sase-xe.16.11.6.1] PROPOSED FOLLOW-UP: Investigate pager copy-link test flake - tests/pager/test_app_actions.py::test_y_then_label_copies_the_links_resolved_path failed in the first full just check run, then passed unchanged on direct rerun.

[2026-09-09T17:39:23Z · sase-xe.16.11.6.1] Verified cargo test -p sase_core federation_, cargo test -p sase_core_py fleet_contract_bindings_round_trip_nested_dicts, focused Python fleet/binding regressions, just _lint-symvision, and SASE_CORE_DIR=sase/repos/external/gh/sase-org/sase-core just check.

## Dependencies

- **Blocks:** [sase-xe.16.11.6.2](sase-xe.16.11.6.2.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.6.1/README.md) | [sase-xe.16.11.6.1](sase-xe.16.11.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8c8dfc3`](https://github.com/sase-org/sase/commit/8c8dfc3f6b08a1ce26304fff822f339c9c84b591) | feat(fleet): consume Rust federation counts | [sase-xe.16.11.6.1](sase-xe.16.11.6.1.md) | 2026-09-09 15:02:16 EDT |

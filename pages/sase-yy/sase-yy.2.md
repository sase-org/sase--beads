# Bead: sase-yy.2 — Immutable link-event contract and reducer in Rust core

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.2` · **Size:** large
**Created:** 2026-09-09 11:48:16 EDT · **Closed:** 2026-09-09 13:07:16 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

event-contract: define content-addressed link-event files, canonical serialization, operation identity, and a deterministic event-set reducer in sase-core with Python bindings, beside the landed publication-policy module.

## Notes

[2026-09-09T16:22:51Z · sase-yy.2] PROPOSED FOLLOW-UP: release floor ratchet - PyPI already has sase-core-rs 0.32.55 without the artifact_link_event_* API from this phase; after release-plz publishes the next feature release from this change (expected 0.33.0), update pyproject.toml and uv.lock to require sase-core-rs>=0.33.0,<0.34.0 and rerun tools/validate_sase_core_rs.

[2026-09-09T17:07:16Z · sase-yy.2] Implemented immutable artifact link event contract/reducer in Rust core with PyO3 bindings and SASE validator coverage. Verified: cargo fmt --all; cargo test -p sase_core artifact_link::events; cargo test -p sase_core_py artifact_ref_contract_bindings_round_trip_json_shapes; LD_LIBRARY_PATH-adjusted just check in sase-core; tools/validate_sase_core_rs against rebuilt local extension; focused validator pytest; SASE just check. Reducer coverage includes duplicate retry idempotence, operation-id collision rejection, alias chains/cycles/conflicts, baseline import one-shot preservation, predecessor checks, supersession, and add-wins remove ordering. No epic symbols were registered for this bead.

## Dependencies

- **Blocks:** [sase-yy.3](sase-yy.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.5](sase-yy.5.md) ✓ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.2.md) | [sase-yy.2](sase-yy.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`232ffbb`](https://github.com/sase-org/sase/commit/232ffbba3fdd9011f4c35d4a392c59d699df7709) | test: validate artifact link event bindings | [sase-yy.2](sase-yy.2.md) | 2026-09-09 13:09:25 EDT |
| sase-core | [`sase-core@528c3db`](https://github.com/sase-org/sase-core/commit/528c3dbd7ee3dd6a1a6de221287cb73d1b37b7ac) | feat: add artifact link event contract | [sase-yy.2](sase-yy.2.md) | 2026-09-09 13:12:27 EDT |

# Bead: sase-11l.5.1.2.1.1 — Rust hold store, launch armer, and wire support

[Bead Pages](../README.md) / [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) / sase-11l.5.1.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.1` · **Size:** medium
**Created:** 2026-09-16 16:01:37 EDT · **Closed:** 2026-09-16 17:07:54 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

## Description

hold-core: add the `launch` armer kind, arm-time kin rejection, and armer rebind to the Rust hold store. Add a pure launch-unit armer builder and key helper, a `future` edge in the typed hold-cycle check, and a waiting-marker wire that keeps "absent" separate from "false" for `wait_priority_explicit`. Add pyo3 bindings and bump the core pin.

## Notes

[2026-09-16T21:07:54Z · sase-11l.5.1.2.1.1] Implemented Rust hold-core: launch armer kind/liveness, arm-time kin rejection, keyed rebind, launch hold key/armer helpers, future cycle edges, tri-state wait_priority_explicit, and pyo3 bindings. Verified cargo test -p sase_core agent_hold; cargo test -p sase_core agent_launch; cargo test -p sase_core agent_scan; cargo test -p sase_core --test agent_scan_parity waiting_marker_carries_runner_slot_fields; cargo test -p sase_core_py; SASE_ALLOW_STALE_CORE=1 just rust-dev-install local .venv; tools/check_sase_core_rs_bindings; tools/validate_sase_core_rs --sase-core-dir linked sase-core; just check; epic-symbols clean. Core pin not bumped because the linked core commit is unpublished; used local dev install per plan fallback.

## Dependencies

- **Blocks:** [sase-11l.5.1.2.1.2](sase-11l.5.1.2.1.2.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.1/README.md) | [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f93ed13`](https://github.com/sase-org/sase-core/commit/f93ed139f4b1295d7c508a90cf822be9f229e75c) | feat(agent-hold): add launch armer core support | [sase-11l.5.1.2.1.1](sase-11l.5.1.2.1.1.md) | 2026-09-16 17:09:25 EDT |

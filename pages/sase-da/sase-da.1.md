# Bead: sase-da.1 — Fair, configurable store-lock waits in sase-core

[Bead Pages](../README.md) / [sase-da](README.md) / sase-da.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r5/README.md) · **Assignee:** `sase-da.1` · **Size:** medium
**Created:** 2026-08-01 13:03:54 UTC · **Closed:** 2026-08-01 13:58:21 UTC
**Plan:** [202608/bead\_store\_lock\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_store_lock_contention.md)

## Description

store_lock: replace the 2s hardcoded try-lock poll in the Rust bead-mutation, task-store, and prompt-stash locks with a capped-backoff wait whose bound is a long, env-overridable default, and record holder identity so an expired wait names its blocker.

## Notes

[2026-08-01T13:43:08Z · sase-da.1] PROPOSED FOLLOW-UP: Stabilize Config Center populated PNG snapshot selection — test_config_center_config_tab_png_snapshot deterministically renders the selected axe.chop_script_dirs field detail while its golden expects the axe section summary, producing a 0.953285% pixel mismatch in isolated reruns; unrelated to store-lock changes.

[2026-08-01T13:58:21Z · sase-da.1] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace pass in sase-core; the focused lock suite proves acquisition after >2s, env parsing, deadline-bounded backoff, holder PID/operation timeout messages, holder cleanup, doctor tolerance, and lock_wait_ms reporting. Rebuilt sase_core_rs with just install; SASE_PYTEST_EXCLUDE_VISUAL=1 just check passes, and focused bead-store ignore tests pass. The unrelated deterministic Config Center PNG mismatch is recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-da.4](sase-da.4.md) ◐
- **Blocks:** [sase-da.5](sase-da.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-da.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-da.1/README.md) | [sase-da.1](sase-da.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`ecc1e90`](https://github.com/sase-org/sase/commit/ecc1e901bd49142fcf91a80fa50dcff789752d7c) | fix: ignore bead mutation holder metadata | [sase-da.1](sase-da.1.md) | 2026-08-01 14:00:41 |

# Bead: sase-17.6 — Phase 2F: Verification, Benchmarks, and Rollout Decision

[Bead Pages](../README.md) / [sase-17](README.md) / sase-17.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-17.6`
**Created:** 2026-04-29 06:53:53 UTC · **Closed:** 2026-04-29 08:16:11 UTC
**Plan:** [202604/rust\_backend\_phase2\_query.md](https://github.com/sase-org/sase--plans/blob/main/202604/rust_backend_phase2_query.md)

## Description

Decide whether the Rust query backend should remain opt-in, become the default, or be skipped because Python is fast enough. Run sase_101 checks (just install, focused tests, just rust-install, just bench-core, just bench-query if added, just check) and ../sase-core checks (cargo fmt --check, cargo clippy -D warnings, cargo test --workspace). Measure parse-only and parse+evaluate at 100/1k/10k specs plus dual-run overhead. Apply the >=2x research go gate. Document the result in a handoff or research update.

## Notes

Verification & rollout: keep Rust query backend opt-in. Python batch path 18-21% faster than per-row; Rust facade 12-15x slower at 10k specs due to FFI/serde dict conversion cost. Does not clear 2x gate. See sdd/research/202604/rust_backend_phase2_query_handoff.md.

## Dependencies

- **Depends on:** [sase-17.5](sase-17.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`40c9bed`](https://github.com/sase-org/sase/commit/40c9bed3af5c1860db39dcd4a18a4582303dd06b) | chore(core): Phase 2F — verification, benchmarks, and rollout decision (sase-17.6) | [sase-17.6](sase-17.6.md) | 2026-04-29 08:19:30 |

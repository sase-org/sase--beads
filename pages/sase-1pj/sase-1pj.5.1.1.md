# Bead: sase-1pj.5.1.1 — Define staged monitor and ToolRun reservation contracts

[Bead Pages](../README.md) / [sase-1pj.5.1](sase-1pj.5.1.md) / sase-1pj.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.md) · **Assignee:** `sase-1pj.5.1.1` · **Size:** medium
**Created:** 2026-10-29 14:48:36 EDT · **Closed:** 2026-10-29 18:01:23 EDT
**Plan:** [202610/monitor\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_staging.md)

## Description

contracts: implement Rust-owned staged monitor payload validation, staged-owner liveness and self-wait decisions, and atomic ToolRun join reservation/activation/release. Add bindings, contract tests, thin Python adapters, and the required core revision pin. Keep public monitor starts on their existing path until activation.

## Notes

[2026-10-29T20:28:53Z · sase-1pj.5.1.1] Progress: Rust contracts + bindings + Python adapters + contract tests implemented and green (Rust staged_handoff/staged_join/prepared_reservation unit tests pass; sase_core_py 370 pass; 15 Python contract tests pass; symvision clean). sase-core `sase tool run check` (run f5f47f7b0b5093c86232d63010ee52a7) still running; sase-repo `just check` and bead close remain.

[2026-10-29T20:57:50Z · sase-1pj.5.1.1--1] PROPOSED FOLLOW-UP: sase_gateway IPC test listener_creates_private_socket_and_rejects_symlink flaked under host load (loadavg ~27) in full sase-core check run f5f47f7b0b5093c86232d63010ee52a7 with AlreadyRunning lock error; passes in isolation and full -p sase_gateway --lib rerun showed 243 passed — consider serializing or hardening that test

[2026-10-29T22:01:23Z · sase-1pj.5.1.1--2] Contracts complete: staged payload validation (validate_staged_handoff, launch payload round-trip/version, unknown-field/bad-digest rejection), staged membership (running preserves behavior, staged has no supervisor/capacity), staged-owner liveness (pending before proc), self-wait (requires durable stage ownership, ignores name coincidence), atomic ToolRun join reserve/activate/release (blocks other joiners, validates starter, terminal-after-reserve activates; ordinary joins unaffected), prepared-reservation ownership (reserve/bind/release round-trip, stage isolation, monitor-mismatch refusal). Rust staged_handoff 33 passed, staged_join 6 passed, prepared_reservation 6 passed; Python tests/test_staged_monitor_contracts.py 15 passed; sase_core_py 370 passed in prior run. sase-core check f5f47f7b 242 passed 1 flaky IPC AlreadyRunning (passes isolated, gateway rerun 243 passed, in PROPOSED FOLLOW-UP); sase-repo check a4d0f1b 58865 passed 18 skipped, 4 failed triaged no_new_failures (3 KNOWN 1 FLAKY, none on phase files), all lint incl symvision green. Public monitor starts unchanged (no monitor files in diff). sase-core-revision.txt pin ratchet for new unpublished bindings awaits host landing.

## Dependencies

- **Blocks:** [sase-1pj.5.1.2](sase-1pj.5.1.2.md) ◐ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.5.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.1.md) | [sase-1pj.5.1.1](sase-1pj.5.1.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2a62513`](https://github.com/sase-org/sase-core/commit/2a625131e32f8d8e6c935683834d241a0651d06c) | feat(staged-monitor): add Rust-owned staged payload and ToolRun reservation contracts | [sase-1pj.5.1.1](sase-1pj.5.1.1.md) | 2026-10-29 18:25:55 EDT |
| sase | [`b175b63`](https://github.com/sase-org/sase/commit/b175b6375855c7d8e2c0a5aece625e04e22e78d2) | feat(staged-monitor): wire Rust-owned staged payload and reservation contracts | [sase-1pj.5.1.1](sase-1pj.5.1.1.md) | 2026-10-29 19:59:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.5.1.1--2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.5.1.1.md

<!-- sase:referenced-by:end -->

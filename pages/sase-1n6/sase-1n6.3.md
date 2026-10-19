# Bead: sase-1n6.3 — Exact core pin and the shared core-ensure rule

[Bead Pages](../README.md) / [sase-1n6](README.md) / sase-1n6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11y](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11y.md) · **Assignee:** `sase-1n6.3` · **Size:** medium
**Created:** 2026-10-19 16:40:08 EDT · **Closed:** 2026-10-19 17:39:33 EDT
**Plan:** [202610/e2\_release\_train\_steward.md](https://github.com/sase-org/sase--plans/blob/main/202610/e2_release_train_steward.md)

## Description

core-pin: ratchet_core_pin writes sase-core-rs==X.Y.Z chosen by one shared core-ensure rule, master converts to the exact form, and every tool that assumed a window accepts the pin.

## Notes

[2026-10-19T21:39:10Z · sase-1n6.3] PROPOSED FOLLOW-UP: Unrelated just-check scoped NEW failures (axe chop bead-claim checks, agent-load production oracle, stats argparse help metavar, agents-sync bounded drain, dismiss persistence) — not caused by the exact-pin/core-ensure work; they do not touch ratchet_core_pin, _release_core.py, or the pin specifier.

[2026-10-19T21:39:33Z · sase-1n6.3] Exact pin landed: tools/_release_core.py core-ensure (PINNED/CORE_LAG, GitHub then urllib then local-git, skip pre-suffix tags); tools/ratchet_core_pin writes ==X.Y.Z, refuses backwards, CORE_LAG changes nothing; master is sase-core-rs==0.42.0; validator classifies == as behind(3)/ahead(4). Verified: live report-only printed CORE_LAG(pin=f0f2275f9d38db3dc4e80aa4c2635017696a7e93, newest_complete=0.42.1); uv lock --check; just install-venv with and without SASE_CORE_WHEEL (0.42.0 wheel); publish.yml uses ratchet_core_pin; 154 phase-owned tests passed including contract_manifest (78) and exact-pin validator/ratchet tests. just check lint/fmt passed; remaining scoped NEW failures are unrelated (PROPOSED FOLLOW-UP). No --epic-symbol leftovers. Did not close parent sase-1n6.

## Dependencies

- **Blocks:** [sase-1n6.5](sase-1n6.5.md) ◐ · ⧖ 2026-10-19
- **Blocks:** [sase-1n6.7](sase-1n6.7.md) ◐ · ⧖ 2026-10-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.3/README.md) | [sase-1n6.3](sase-1n6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`befa41b`](https://github.com/sase-org/sase/commit/befa41b575abbc0745bd7aa33019126760110a58) | feat(release): pin sase-core-rs to an exact published version | [sase-1n6.3](sase-1n6.3.md) | 2026-10-19 19:34:39 EDT |

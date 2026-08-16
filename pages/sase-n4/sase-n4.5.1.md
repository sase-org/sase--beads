# Bead: sase-n4.5.1 — Make first usage-limit disable atomic in sase-core

[Bead Pages](../README.md) / [sase-n4.5](sase-n4.5.md) / sase-n4.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-n4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n4.land.md) · **Assignee:** `sase-n4.5.1` · **Size:** medium
**Created:** 2026-08-16 14:19:24 EDT · **Closed:** 2026-08-16 15:20:09 EDT
**Plan:** [202608/finish\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_usage_limit_auto_disable.md)

## Description

atomic-disable: add a Rust-core and Python-binding operation that atomically writes a provider disable only when no active record exists, returns whether this caller won the window, preserves the existing unconditional manual replacement APIs, and proves first-writer behavior under real contention.

## Notes

[2026-08-16T19:17:23Z · sase-n4.5.1] API for sase-n4.5.2: Python try_disable_provider / try_disable_provider_until return ProviderDisableWriteOutcome(inserted, record). Bindings provider_disable_try_set_relative/until return {version, inserted, record}. Unconditional disable_provider/_until unchanged. Landed in sase-core dc87c8e.

[2026-08-16T19:18:06Z · sase-n4.5.1] PROPOSED FOLLOW-UP: ratchet sase-core-rs floor after release-plz publishes the first-writer try-set bindings — probe still reports blocked_unpublished against 0.27.11

[2026-08-16T19:18:44Z · sase-n4.5.1] PROPOSED FOLLOW-UP: bead CLI stats golden is missing the Flags: 0 row from sase-core 0.27.14 flag types — tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats]

[2026-08-16T19:19:19Z · sase-n4.5.1] PROPOSED FOLLOW-UP: tests/test_file_panel.py static/live render tests fail with mock.update not called / NoneType subscript — unrelated to provider-disable

[2026-08-16T19:20:09Z · sase-n4.5.1] Added Rust try_set_provider_disable_{relative,until} that prune+decide+write under the existing lock and return {version, inserted, record}; unconditional setters unchanged. Verified 8-way barrier contention (one winner, stable record, sibling preserved), expired replacement, no-mutate on existing, and lock timeout. Bindings plus Python try_disable_provider/_until and ProviderDisableWriteOutcome; process-contention, smoke first-writer, and validate_sase_core_rs first-writer probe passed. just install rebuilt local sase-core-rs. just check lint passed; scoped run escalated (justfile + core-identity) with 7 unrelated failures (bead stats Flags golden, file_panel render). Landed sase-core dc87c8e.

[2026-08-16T19:22:00Z · sase-n4.5.1] Python first-writer facade try_disable_provider/_until plus ProviderDisableWriteOutcome; validator first-writer probe; process-contention and smoke tests; docs/Justfile epic-symbols. Unconditional setters unchanged. just check lint passed; scoped suite escalated with unrelated failures recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-n4.5.2](sase-n4.5.2.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.5.1/README.md) | [sase-n4.5.1](sase-n4.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dc87c8e`](https://github.com/sase-org/sase-core/commit/dc87c8e5faa250b1babc84764493e05233d5a0a8) | feat(provider\_disable): add atomic first-writer disable | [sase-n4.5.1](sase-n4.5.1.md) | 2026-08-16 15:15:23 EDT |

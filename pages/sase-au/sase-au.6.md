# Bead: sase-au.6 — Land the cross-repo contract, snapshots, and documentation

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.6` · **Size:** medium
**Created:** 2026-07-29 16:26:40 UTC · **Closed:** 2026-07-29 18:46:33 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

land: raise the sase-core-rs floor together with the Python artifact-index schema constant, verify the feature end to end against real recorded data, add the new PNG visual snapshots, and document the sub-tab and its keys.

## Notes

[2026-07-29T18:46:33Z · sase-au.6] Raised sase-core-rs floor to >=0.12.11 with artifact-index schema 19 and strengthened the schema-4 xprompts contract probe. Verified a schema-18 temporary index over real history rebuilt 5,470 rows once and the second refresh was a no-op; direct xprompts.json aggregation exactly matched the Rust query (4,883 runs, 4,802 with xprompts, 81 without, 9,901 refs, identical top five), including focus and project-filter payloads. Added and visually reviewed four XPrompts PNG snapshots; SASE_PYTEST_WORKERS=4 just test-visual passed 379 tests (1 skipped). just check static gates passed and the full matrix reached 23,745 passed with one unrelated task-list glyph shared-state flake; that test's complete 13-test module passed in isolation.

[2026-07-29T18:47:27Z · sase-au.6] Verified the dependency/schema landing contract, real-data XPrompt aggregation and stale-schema rebuild lifecycle, four reviewed PNG snapshots, 379 visual tests passing with 1 skipped, targeted contract tests passing, and the only broad-suite holdout as an unrelated task-list shared-state flake whose full 13-test module passes in isolation.

## Dependencies

- **Depends on:** [sase-au.2](sase-au.2.md) ✓
- **Depends on:** [sase-au.5](sase-au.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-au.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-au.6/README.md) | [sase-au.6](sase-au.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d0b2ed9`](https://github.com/sase-org/sase/commit/d0b2ed97cde8d15ab71afa62d7be06da1cb816f1) | feat(ace): finalize xprompt statistics contract | [sase-au.6](sase-au.6.md) | 2026-07-29 18:49:22 |

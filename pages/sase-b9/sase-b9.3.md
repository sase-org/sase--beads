# Bead: sase-b9.3 — Consumption on \`sase artifact show\` and \`--unused\` on \`sase artifact list\`

[Bead Pages](../README.md) / [sase-b9](README.md) / sase-b9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b9.3` · **Size:** medium
**Created:** 2026-07-30 14:36:44 UTC · **Closed:** 2026-07-30 16:00:00 UTC
**Plan:** [202607/artifact\_consumption\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_consumption_ledger.md)

## Description

read-surfaces: add the Rust-backed summary facade, report consumption counts and consuming agents for any reference, and add the alphabetized `-u/--unused` list filter that reaches the query rather than post-filtering it.

## Notes

[2026-07-30T16:00:00Z · sase-b9.3] Implemented Rust-backed consumption summaries for artifact show (pretty and additive JSON, including fragment-free joins) and wired alphabetized -u/--unused through the v3 Rust query before limit with filtered panel labeling. Verified 76 focused CLI/query/ledger/e2e tests pass; full suite reached 24,299 passed and 7 skipped, and all 3 reported failures passed in isolated reruns after updating parser expectations. just check passes every format/lint gate and stops only at 6 pre-existing SDD prompt-link validation errors across the artifact-consumption, artifact-lifecycle, and family-provenance plans.

## Dependencies

- **Depends on:** [sase-b9.2](sase-b9.2.md) ✓
- **Blocks:** [sase-b9.4](sase-b9.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-b9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-b9.3/README.md) | [sase-b9.3](sase-b9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`a4880ce`](https://github.com/sase-org/sase/commit/a4880ce321df4a9afdf1a2be5ce86eed8a5860fe) | feat(artifact): expose consumption read surfaces | [sase-b9.3](sase-b9.3.md) | 2026-07-30 16:01:51 |

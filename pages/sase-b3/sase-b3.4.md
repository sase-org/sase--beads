# Bead: sase-b3.4 — Zero-marshalling payload index binding

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.4` · **Size:** medium
**Created:** 2026-07-30 08:18:27 UTC · **Closed:** 2026-07-30 09:01:59 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

binding: add the opaque AtReferenceInventory pyclass built once off-thread, let at_reference_menu accept it instead of re-marshalling every payload row per keystroke, and expose the fuzzy matcher to Python.

## Notes

[2026-07-30T09:03:30Z · sase-b3.4] Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and the release-mode 5,000-row indexed at_reference_menu benchmark under the 8 ms mean gate; pushed sase-core commit 1290667.

## Dependencies

- **Depends on:** [sase-b3.3](sase-b3.3.md) ✓
- **Blocks:** [sase-b3.6](sase-b3.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-b3.4 | [sase-b3.4](sase-b3.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1290667`](https://github.com/sase-org/sase-core/commit/12906673cb769a4c2f9d9d499df4968e2132329c) | feat(editor): add indexed at-reference payload binding | [sase-b3.4](sase-b3.4.md) | 2026-07-30 09:02:20 |

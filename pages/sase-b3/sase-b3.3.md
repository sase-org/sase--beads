# Bead: sase-b3.3 — Fuzzy at-reference menu and match runs on the wire

[Bead Pages](../README.md) / [sase-b3](README.md) / sase-b3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b3.3` · **Size:** medium
**Created:** 2026-07-30 08:18:23 UTC · **Closed:** 2026-07-30 08:41:44 UTC
**Plan:** [202607/fuzzy\_artifact\_ref\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/fuzzy_artifact_ref_completion.md)

## Description

menu: rewire build_at_reference_menu onto the fuzzy matcher for kinds, payloads, and the path partial; make payload rows carry the payload as their label plus title, match runs, and tier; keep empty-query order and prefix-only Tab extension.

## Notes

[2026-07-30T08:43:08Z · sase-b3.3] Implemented fuzzy kind, payload, and trailing-path menu matching with path-first payload labels, titles, match runs/tiers, payload/truncation counts, deterministic empty-query ordering, and prefix-only Tab extension. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, cargo test --workspace, and pushed sase-core commit b5c99ce.

## Dependencies

- **Depends on:** [sase-b3.1](sase-b3.1.md) ✓
- **Blocks:** [sase-b3.4](sase-b3.4.md) ✓
- **Blocks:** [sase-b3.5](sase-b3.5.md) ✓

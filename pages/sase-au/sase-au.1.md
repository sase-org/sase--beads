# Bead: sase-au.1 — Project launch-boundary xprompt usage into the artifact scan record and index

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.1` · **Size:** medium
**Created:** 2026-07-29 16:26:08 UTC · **Closed:** 2026-07-29 16:35:24 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

core-scan: in sase-core, add a UsedXPromptWire projection of each artifact directory's xprompts.json to the agent-artifact scan record, sign that file so stale rows re-index, and bump the artifact index schema so existing indexes rebuild with the new projection.

## Notes

[2026-07-29T16:35:24Z · sase-au.1] Verified launch-boundary xprompts.json projection/deduplication and soft-error handling, late-file signature reindexing, and schema 18→19 xprompts_sig upgrade; cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace all pass.

## Dependencies

- **Blocks:** [sase-au.2](sase-au.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-au.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-au.1/README.md) | [sase-au.1](sase-au.1.md) | 0 |

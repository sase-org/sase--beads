# Bead: sase-tt.4 — Direct dict-to-QueryRow corpus construction in sase-core

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.4` · **Size:** medium
**Created:** 2026-08-25 14:59:14 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

core-corpus: remove the serde_json::Value intermediate from `compile_corpus_with_profile` in the sase-core repo so corpus indexing stops materializing every row twice on the Rust side, then release and raise the floor.

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.4/README.md) | [sase-tt.4](sase-tt.4.md) | 0 |

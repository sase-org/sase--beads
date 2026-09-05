# Bead: sase-ws.5 — Drop orphaned Rust import APIs

[Bead Pages](../README.md) / [sase-ws](README.md) / sase-ws.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.kellys\_mbp.y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.kellys_mbp.y.md) · **Assignee:** `sase-ws.5` · **Size:** medium
**Created:** 2026-09-04 13:48:31 EDT
**Plan:** [202609/remove\_agents\_sync\_import.md](https://github.com/sase-org/sase--plans/blob/main/202609/remove_agents_sync_import.md)

## Description

rust-core-cleanup: remove sase-core identity and wire surface whose only callers were the deleted Python import leg, keeping anything still needed to read historical local state, and update bindings and parity tests.

## Dependencies

- **Depends on:** [sase-ws.4](sase-ws.4.md) ◐ · ⧖ 2026-09-04
- **Blocks:** [sase-ws.6](sase-ws.6.md) ◐ · ⧖ 2026-09-04

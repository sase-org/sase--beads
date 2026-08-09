# Bead: sase-ik.1 — Match phrases across one line break and expose per-line span segments

[Bead Pages](../README.md) / [sase-ik](README.md) / sase-ik.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ws](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ws/README.md) · **Assignee:** `sase-ik.1` · **Size:** medium
**Created:** 2026-08-09 15:53:57 EDT · **Closed:** 2026-08-09 16:11:53 EDT
**Plan:** [202608/glossary\_line\_break\_matching.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_line_break_matching.md)

## Description

core: allow a single line break inside a multiword alias in the Rust matcher, add core-computed per-line display segments to the glossary span wire, and emit one LSP semantic token per segment.

## Notes

[2026-08-09T20:11:53Z · sase-ik.1] Implemented core matcher segments and LSP token splitting; verified just install, just rust-fmt, just rust-check, cargo test --workspace glossary, and cargo test --workspace all pass.

[2026-08-09T20:13:28Z · sase-ik.1] Verified just install, just rust-fmt, just rust-check, cargo test --workspace glossary, and cargo test --workspace.

[2026-08-09T20:20:50Z · sase-ik.1] Reconstructed the linked core patch after checkout refresh; verified cargo test --workspace glossary, just rust-fmt, just rust-check, and cargo test --workspace.

## Dependencies

- **Blocks:** [sase-ik.2](sase-ik.2.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ik.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ik.1/README.md) | [sase-ik.1](sase-ik.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4012af5`](https://github.com/sase-org/sase-core/commit/4012af5b871a9550210f87e9af133259b430bdcc) | feat(glossary): match phrases across line breaks | [sase-ik.1](sase-ik.1.md) | 2026-08-09 16:21:30 EDT |

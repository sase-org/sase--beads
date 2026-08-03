# Bead: sase-f2.5 — Rust prompt\_xprompt module removal

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.5` · **Size:** small
**Created:** 2026-08-03 14:48:45 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

core: delete the `prompt_xprompt` module and its three PyO3 bindings from the sibling Rust core repository while keeping the shared `prompt_rewrite` helper the artifact rewriter still uses.

## Dependencies

- **Depends on:** [sase-f2.3](sase-f2.3.md) ◐
- **Depends on:** [sase-f2.4](sase-f2.4.md) ◐

# Bead: sase-1oe.2 — A failed core cut stops counting as red once a newer cut succeeds

[Bead Pages](../README.md) / [sase-1oe](README.md) / sase-1oe.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14h.md) · **Assignee:** `sase-1oe.2` · **Size:** small
**Created:** 2026-10-26 08:35:12 EDT
**Plan:** [202610/unblock\_e2\_release\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_release_cutover.md)

## Description

cut-red: in sase-core, handle_no_train reports CoreCutRed only when the newest decisive completed cut is a typed failure. A later successful cut supersedes a stale red cut. Rust state tests and the steward state docs row are updated.

## Dependencies

- **Blocks:** [sase-1oe.3](sase-1oe.3.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oe.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oe.2/README.md) | [sase-1oe.2](sase-1oe.2.md) | 0 |

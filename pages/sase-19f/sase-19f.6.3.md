# Bead: sase-19f.6.3 — Accept and preserve multiplier capacity in wait and directive editors

[Bead Pages](../README.md) / [sase-19f.6](sase-19f.6.md) / sase-19f.6.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.land.md) · **Assignee:** `sase-19f.6.3` · **Size:** medium
**Created:** 2026-09-26 04:40:45 EDT
**Plan:** [202609/queue\_multiplier\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_surfaces.md)

## Description

edit-capacity: Teach the wait modal, wait actions, directive persistence, agent directive command, and prompt queue editing to accept <M>x through the Rust-backed parser. Prefill authored 1.5x, clear the opposite capacity form on edits, and preserve the multiplier on priority-only or weight-only changes. Add focused modal, persistence, and prompt-edit tests; run just check in sase.

## Dependencies

- **Depends on:** [sase-19f.6.2](sase-19f.6.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-19f.6.3/README.md) | [sase-19f.6.3](sase-19f.6.3.md) | 0 |

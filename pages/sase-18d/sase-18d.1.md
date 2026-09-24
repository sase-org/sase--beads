# Bead: sase-18d.1 — Rust cleanup wire for live runners and atomic dismissed index

[Bead Pages](../README.md) / [sase-18d](README.md) / sase-18d.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ra](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ra.md) · **Assignee:** `sase-18d.1` · **Size:** medium
**Created:** 2026-09-24 16:28:30 EDT
**Plan:** [202609/x\_kill\_removal\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_removal_reliability.md)

## Description

core-wire: in sase-core, add runner_is_live to the cleanup target wire (schema 5) so a FAILED row with a live runner becomes a kill item. Add an atomic, locked, merge-on-write dismissed-index update API. Then update the Python wire, the reference planner, the target projection, and the sase-core revision pin in the same change.

## Dependencies

- **Blocks:** [sase-18d.5](sase-18d.5.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.1/README.md) | [sase-18d.1](sase-18d.1.md) | 0 |

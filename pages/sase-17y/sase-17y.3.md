# Bead: sase-17y.3 — Automatic recovery for approved-plan epic launches

[Bead Pages](../README.md) / [sase-17y](README.md) / sase-17y.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0qv](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0qv.md) · **Assignee:** `sase-17y.3` · **Size:** medium
**Created:** 2026-09-24 11:57:14 EDT
**Plan:** [202609/bead\_relocation\_safe\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_relocation_safe_epic_launch.md)

## Description

plan-retry: when a freshly created epic is relocated, remove it by its moved ID, restore the plan's bead_id, publish the rollback, and retry creation (at most 3 attempts); relink a resumed plan to its moved epic and fail with an actionable resume command.

## Dependencies

- **Depends on:** [sase-17y.2](sase-17y.2.md) ◐ · ⧖ 2026-09-24
- **Blocks:** [sase-17y.4](sase-17y.4.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17y.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17y.3/README.md) | [sase-17y.3](sase-17y.3.md) | 0 |

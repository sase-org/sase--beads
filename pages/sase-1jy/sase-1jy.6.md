# Bead: sase-1jy.6 — Persistent scope-key cache so live ticks stat instead of read

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.6` · **Size:** medium
**Created:** 2026-10-11 11:18:38 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

scope-key-cache: persist per-artifact scope keys fingerprinted by agent_meta.json stat data, written only by wait_checks and read by runners, so selection costs one stat per artifact instead of one JSON read.

## Dependencies

- **Depends on:** [sase-1jy.4](sase-1jy.4.md) ◐ · ⧖ 2026-10-11
- **Depends on:** [sase-1jy.5](sase-1jy.5.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jy.6/README.md) | [sase-1jy.6](sase-1jy.6.md) | 0 |

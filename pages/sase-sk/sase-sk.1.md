# Bead: sase-sk.1 — Durable typed admission for AXE chop proposals

[Bead Pages](../README.md) / [sase-sk](README.md) / sase-sk.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c1.md) · **Assignee:** `sase-sk.1` · **Size:** medium
**Created:** 2026-08-23 16:21:06 EDT · **Closed:** 2026-08-23 17:23:22 EDT
**Plan:** [202608/toobig\_split\_conditional\_admission.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_conditional_admission.md)

## Description

axe-chop-typed-admission: route flag-enabled AXE proposals containing %if or %proc through the existing durable typed coordinator, preserve per-proposal chop ownership across detached waits, and settle skipped/error/launched units correctly in chop lifecycle state.

## Notes

[2026-08-23T21:23:22Z · sase-sk.1] Implemented durable typed AXE chop admission for conditional/proc proposals; verified just install, just fmt, focused AXE tests (19 passed), adjacent typed/proc tests (24 passed), just check, and epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-sk.2](sase-sk.2.md) ◐ · ⧖ 2026-08-23
- **Blocks:** [sase-sk.3](sase-sk.3.md) ◐ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sk.1/README.md) | [sase-sk.1](sase-sk.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`faed143`](https://github.com/sase-org/sase/commit/faed143237163b5618384fb60eb9bc16947a36bf) | feat(axe): route chop proposals through typed admission | [sase-sk.1](sase-sk.1.md) | 2026-08-23 17:24:39 EDT |

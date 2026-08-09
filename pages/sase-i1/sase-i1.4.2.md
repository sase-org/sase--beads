# Bead: sase-i1.4.2 — Correct core match semantics and the literal fast path

[Bead Pages](../README.md) / [sase-i1.4](sase-i1.4.md) / sase-i1.4.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.land/README.md) · **Assignee:** `sase-i1.4.2` · **Size:** medium
**Created:** 2026-08-09 09:05:34 EDT
**Plan:** [202608/bead\_search\_regex\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex_landing.md)

## Description

core-correctness: separate match truth from highlight ranges, restore the cheap literal path, support zero-width regex matches, unify errors, and add Rust tests.

## Dependencies

- **Blocks:** [sase-i1.4.3](sase-i1.4.3.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.4.2/README.md) | [sase-i1.4.2](sase-i1.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@49650a0`](https://github.com/sase-org/sase-core/commit/49650a074294d9175b9a36f30ee891841ef032cb) | fix(bead): correct regex search match semantics | [sase-i1.4.2](sase-i1.4.2.md) | 2026-08-09 09:14:48 EDT |

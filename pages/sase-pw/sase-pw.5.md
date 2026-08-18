# Bead: sase-pw.5 — Artifacts scope and Stitches startup filter

[Bead Pages](../README.md) / [sase-pw](README.md) / sase-pw.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.062.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.062.f1.md) · **Assignee:** `sase-pw.5` · **Size:** medium
**Created:** 2026-08-18 11:30:34 EDT · **Closed:** 2026-08-18 15:42:54 EDT
**Plan:** [202608/current\_project.md](https://github.com/sase-org/sase--plans/blob/main/202608/current_project.md)

## Description

artifacts: seed the shared Artifacts project scope from the current project and make it the single owner of the Stitches startup project filter, replacing the synchronous cwd-derived seed.

## Notes

[2026-08-18T19:42:54Z · sase-pw.5--3] Artifacts seeds from current project (MRU, cwd fallback in the worker); Stitches no longer does a synchronous cwd read at startup; precedence is explicit query > session pick > current project > sole enabled > all; seed_filters:false restores today; mid-session MRU/pick-all does not re-scope; CLI completion spec snapshot regenerated so flag new matches the argparse tree; stale sase-pw.4 epic-symbols re-keyed to sase-pw / sase-pw.8 so just check stays green. just check passed (fmt, lint including symvision, SASE validation, scoped tests escalated to full suite).

[2026-08-18T19:44:11Z · sase-pw.5--3] Artifacts seeds from current project (MRU, cwd fallback in the worker); Stitches no longer does a synchronous cwd read at startup; precedence is explicit query > session pick > current project > sole enabled > all; seed_filters:false restores today; mid-session MRU/pick-all does not re-scope; CLI completion spec snapshot regenerated so flag new matches the argparse tree; stale sase-pw.4 epic-symbols re-keyed to sase-pw / sase-pw.8. just check passed (fmt, lint including symvision, SASE validation, scoped tests escalated to full suite).

## Dependencies

- **Depends on:** [sase-pw.1](sase-pw.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-pw.3](sase-pw.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pw.9](sase-pw.9.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pw.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-pw.5.md) | [sase-pw.5](sase-pw.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d6f88f7`](https://github.com/sase-org/sase/commit/d6f88f7b9e73d148ee15e5e01430a9b6ba4b9e0c) | feat(tui): seed Artifacts scope from the current project | [sase-pw.5](sase-pw.5.md) | 2026-08-18 15:46:22 EDT |

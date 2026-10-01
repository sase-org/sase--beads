# Bead: sase-1dr.9 — Timeline picker with two-point compare

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.9` · **Size:** medium
**Created:** 2026-09-30 19:09:32 EDT · **Closed:** 2026-10-01 10:42:43 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

timeline-picker: add the `@` modal timeline over all versions, including worktree and staged rows and a hidden-versions summary row. It has vim-style list keys, a `/` filter across section, agent, bead, and words, `⏎` jumps that push a trail entry, `=` to compare the row with the open version, and `.` to toggle hidden versions. It stays fast on timelines with hundreds of versions. Add visual goldens.

## Notes

[2026-10-01T13:11:28Z · sase-1dr.9] PROPOSED FOLLOW-UP: symvision flags StarterResolution in src/sase/tool/starter.py as unused on the clean base tree (no consumers in src or tests; unrelated to timeline-picker) — triage it alongside the KNOWN owner_ref/HandoffSubmitResult items

[2026-10-01T14:42:43Z · sase-1dr.9] Timeline picker done: @ modal with worktree/staged rows, hidden summary, j/k/g/G + enter(trail push) + =(two-point compare via explicit_base pin) + . hidden toggle + / filter over section/agent/bead/words, windowed render (500-version perf test), footer @ timeline + help Time row. Verified: 21 focused unit/pilot tests green, 8 new picker PNG goldens + 20 footer-only history goldens inspected/approved, ruff/mypy/fmt green, sase tool run check verdict no_new_failures (only KNOWN pre-existing symvision/scoped items; StarterResolution filed as PROPOSED FOLLOW-UP)

## Dependencies

- **Blocks:** [sase-1dr.12](sase-1dr.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.8](sase-1dr.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1dr.9/README.md) | [sase-1dr.9](sase-1dr.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`994d5fe`](https://github.com/sase-org/sase/commit/994d5fe9f9016c213044a7ff074859b6ff395ee3) | feat(pager): add @ timeline picker modal with jump, compare, filter | [sase-1dr.9](sase-1dr.9.md) | 2026-10-01 11:05:29 EDT |

# Bead: sase-14n.8 — Make the notification modal footer fit the modal

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.8` · **Size:** medium
**Created:** 2026-09-20 17:14:16 EDT · **Closed:** 2026-09-21 13:17:49 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

notify_footer: give the notification modal's hint line a width-aware tier ladder so close and +1 stay visible at 120 columns in all three hint variants.

## Notes

[2026-09-21T17:00:37Z · sase-14n.8--1] --list

[2026-09-21T17:17:02Z · sase-14n.8--1] PROPOSED FOLLOW-UP: repo-wide mypy fails on untouched src/sase/dev_update/prebuild.py:134,162 (_run_command vs DevCommandRunner signature), blocking just check for all agents

[2026-09-21T17:17:49Z · sase-14n.8--1] Footer fits 120-col modal: tiers measure 100/87/87 cells at width 108 with q:close and +: +1 visible in all 3 variants; full strings preserved (208/138/153). Fixed self-measurement loop (width:1fr + fallback-width first paint). Verified: 9 footer unit tests pass, 42 incl. neighbors pass, 12 PNG goldens refreshed with diffs confined to footer row 35, visual check clean (14 unchanged), ruff clean, footer mypy clean.

## Dependencies

- **Depends on:** [sase-14n.1](sase-14n.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.2](sase-14n.2.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.4](sase-14n.4.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.5](sase-14n.5.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-14n.6](sase-14n.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.8.md) | [sase-14n.8](sase-14n.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`03fff9d`](https://github.com/sase-org/sase/commit/03fff9dcbcad9c17e62cbc2217033c6be30a6a18) | fix(ace): fit notification modal footer to modal width so close and +1 stay visible | [sase-14n.8](sase-14n.8.md) | 2026-09-21 13:20:25 EDT |

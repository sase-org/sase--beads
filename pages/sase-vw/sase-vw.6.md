# Bead: sase-vw.6 — Generated task-type strand links

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.6` · **Size:** small
**Created:** 2026-08-30 10:02:19 EDT · **Closed:** 2026-08-30 12:33:14 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

taskgen: make the generated task-type strands emit a Related Task Types section linking every other catalog type their own prose names.

## Notes

[2026-08-30T16:32:44Z · sase-vw.6] PROPOSED FOLLOW-UP: test_bare_init_yes_repairs_unreferenced_long_memory asserts "## 3. Reference Memory" / "### 3.1 sase/memory/cli_rules.md" — fails on current tree without this phase (sister tests expect "## 2. Reference Memory"); scoped just check selected it via init_memory import graph

[2026-08-30T16:33:14Z · sase-vw.6] Generated task-type strands emit ## Related Task Types with [[task_types/<slug>]] for other agent-creatable catalog types named in summary/when_to_use/create_refusal (whole-word, slug-sorted; omitted when none). Verified: sase memory show task_types:bug lists ci and flake plus Linked References; feature/memory omit the section; generation tests pass; fmt/ruff/mypy/symvision/toobig green. just check: 914 passed, 1 pre-existing failure test_bare_init_yes_repairs_unreferenced_long_memory (stale ## 3. Reference Memory heading; fails without this phase).

## Dependencies

- **Depends on:** [sase-vw.4](sase-vw.4.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.6/README.md) | [sase-vw.6](sase-vw.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`19a77ee`](https://github.com/sase-org/sase/commit/19a77eea96af28f13f973f191cc0415afd1fcf3d) | feat(memory): emit Related Task Types links on generated strands | [sase-vw.6](sase-vw.6.md) | 2026-08-30 12:34:28 EDT |

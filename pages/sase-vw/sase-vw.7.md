# Bead: sase-vw.7 — Link the existing corpus

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.7` · **Size:** medium
**Created:** 2026-08-30 10:02:19 EDT · **Closed:** 2026-08-30 13:09:36 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

content: add links across the hand-authored notes and strands that already cross-reference each other in prose, and record the decision that supersedes the "not a new, parallel link syntax" clause of the memory-webs record.

## Notes

[2026-08-30T17:09:08Z · sase-vw.7] PROPOSED FOLLOW-UP: Linked References can list the requested strand itself — when an inlined target (bang-link) links back to the requested strand, the back-link is collected as a reference entry, so `sase memory show decisions:gates-never-block` now lists `decisions:gates-never-block` after inlining single-turn-agents. Skip self-addresses when assembling a unit Linked References section.

[2026-08-30T17:09:36Z · sase-vw.7] Verified: sase doctor -C config.memory_webs -s is OK with 0 blockers and 0 unresolved-link warnings. sase memory show lint_and_test.md Linked References lists decisions:two-speed-verification and symvision.md. sase memory show sase_beads.md lists task_types and sase_sizes.md. sase memory show decisions:gates-never-block still inlines single-turn-agents and lists host-owned-completion. sase memory show decisions:memory-links-are-authored lists memory-webs, corpus-before-mechanism, gates-never-block, and sase_artifacts.md. just check passed (fmt, all lint gates, 63 scoped test files).

## Dependencies

- **Depends on:** [sase-vw.5](sase-vw.5.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.7/README.md) | [sase-vw.7](sase-vw.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4509c9d`](https://github.com/sase-org/sase/commit/4509c9d675eaa21485063d99a386c947ab52021a) | docs(memory): link the existing corpus and record authored memory links | [sase-vw.7](sase-vw.7.md) | 2026-08-30 13:10:44 EDT |

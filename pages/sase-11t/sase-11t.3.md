# Bead: sase-11t.3 — Sudo skill foreground-execution guidance

[Bead Pages](../README.md) / [sase-11t](README.md) / sase-11t.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lw.r0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lw.r0.f0.md) · **Assignee:** `sase-11t.3` · **Size:** small
**Created:** 2026-09-16 10:42:01 EDT · **Closed:** 2026-09-16 11:19:03 EDT
**Plan:** [202609/sudo\_gate\_crash\_safe\_handoff.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_gate_crash_safe_handoff.md)

## Description

sudo-skill-foreground-guidance: update the generated sase_sudo skill template to require foreground execution of sase sudo request and to state that any returned tool result means the turn did not end.

## Notes

[2026-09-16T15:19:03Z · sase-11t.3--1] just check passed (exit 0, ~5m34s); verified sase_sudo/sase_gate/sase_run/sase_questions skill template foreground-execution guidance updates and test_init_skills_source_content.py changes. sase bead epic-symbols sase-11t.3 reported no --epic-symbol entries to resolve.

## Dependencies

- **Blocks:** [sase-11t.4](sase-11t.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11t.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11t.3.md) | [sase-11t.3](sase-11t.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9fc5e4d`](https://github.com/sase-org/sase/commit/9fc5e4d5cd884c66ea8e7bf96e3e7f97442c30c0) | docs(skills): add foreground-execution guidance to sudo/gate/run/questions skills | [sase-11t.3](sase-11t.3.md) | 2026-09-16 11:20:29 EDT |

# Bead: sase-11l.5.1.2.1 — Arm %hold at launch submission

[Bead Pages](../README.md) / [sase-11l.5.1.2](sase-11l.5.1.2.md) / sase-11l.5.1.2.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11l.5.1.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11l.5.1.2.md) · **Assignee:** `sase-11l.5.1.2.1.land`
**Created:** 2026-09-16 16:01:36 EDT
**Plan:** [202609/hold\_launch\_arming.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/hold_launch_arming.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/hold_launch_arming.md

<!-- sase:links:end -->

## Description

A launch that carries `%hold` arms a durable hold as soon as it is submitted. For plain agent launches the runner arms the hold before any dependency wait. For typed plans the hold is armed before any unit dispatches. The hold then follows each unit to its runner or proc without losing its original timing. It is released when a unit never dispatches, and it survives every hand-off between processes. The armer never holds its own kin, and a hold-carrying launch gets an implied, non-authored priority boost.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.5.1.2.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.5.1.2.1.land/README.md) | [sase-11l.5.1.2.1](sase-11l.5.1.2.1.md) | 0 |

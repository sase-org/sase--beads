# Bead: sase-p4.2 — Detached epic resume launch

[Bead Pages](../README.md) / [sase-p4](README.md) / sase-p4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05e.md) · **Assignee:** `sase-p4.2` · **Size:** small
**Created:** 2026-08-17 18:53:40 EDT · **Closed:** 2026-08-17 20:18:40 EDT
**Plan:** [202608/epic\_resume\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202608/epic_resume_gate.md)

## Description

launch: add the leased, detached submission helper that runs `sase bead work <epic_id> --yes-to-all` and reuses an in-flight resume instead of double-launching.

## Notes

[2026-08-18T00:18:40Z · sase-p4.2] Added src/sase/bead/epic_resume_launch.py (build_epic_resume_argv, submit_epic_resume_task, active_epic_resume, epic_resume_origin_from_gate_source) mirroring task_launch.py, with tests/test_bead/test_epic_resume_launch.py covering argv construction, single-submission under concurrent calls, reuse of an in-flight resume, and origin mapping. Re-keyed the new public symbols' Justfile --epic-symbol entries to sase-p4.3 (the gate phase that consumes them). Also re-keyed six stale sase-p1.2 --epic-symbol entries (glossary mutation symbols) to sase-p1.6, since sase-p1.2 closed mid-session and those symbols still have no consumer -- unblocks just check for other agents. just install and just check (all lint gates + full escalated test suite, 32573 passed) are green.

## Dependencies

- **Blocks:** [sase-p4.3](sase-p4.3.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p4.2/README.md) | [sase-p4.2](sase-p4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ebdddf1`](https://github.com/sase-org/sase/commit/ebdddf18fa4af17a6ff4a1520e2996e48ef5fd86) | feat(bead): add the detached epic-resume launch helper | [sase-p4.2](sase-p4.2.md) | 2026-08-17 20:24:22 EDT |

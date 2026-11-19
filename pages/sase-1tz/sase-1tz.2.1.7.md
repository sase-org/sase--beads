# Bead: sase-1tz.2.1.7 — Make the publication doctor checks report standing and terminal state

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.7` · **Size:** small
**Created:** 2026-11-19 11:13:27 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

pub_doctor: doctor's agent_publication_outbox check groups issues by (project, signature) and reports audited terminal rows as settled, so the count stays flat across ticks. Apply sase-1rb remedy (a): stale-only protection blocks are not a WARN.

## Notes

[2026-11-19T22:54:08Z · sase-1tz.2.1.7] -l

[2026-11-19T23:40:00Z · sase-1tz.2.1.7] Measurement (athena, pre-install, installed sase): outbox WARN 5202 issues (3856 quarantined, 13 retired, 1333 stale requested revisions); protection WARN 6 enforced blocked, 52 stale, 0 unverified, 16 superseded. After-install commands: sase doctor -C state.agent_publication_outbox -j and sase doctor -C state.agent_publication_protection -j. Post-install expectation: outbox issue count collapses to one group per (project, signature) cause plus settled-terminal counts; protection stays WARN while enforced blocks exist and drops to OK when only stale blocks remain.

[2026-11-19T23:40:11Z · sase-1tz.2.1.7] PROPOSED FOLLOW-UP: symvision NEW finding LaunchPromptContext in src/sase/axe/run_agent_runner_setup_prompt.py reproduces identically on clean HEAD (verified via worktree at 3d3d0f583d); pre-existing and unrelated to pub_doctor, needs its own owner.

[2026-11-19T23:40:16Z · sase-1tz.2.1.7] PROPOSED FOLLOW-UP: sase-1rb remedy (b) — the withheld chat.md bytes on the stale-only protection rows may still be missing from the published sase--agents sidecar; needs a bounded republish through an existing reconcile path, not verifiable from this workspace.

[2026-11-19T23:43:16Z · sase-1tz.2.1.7] Close blocked on merge, not on work: sase bead close refuses while origin/master Justfile still carries the two sase-1tz.2.1.7 --epic-symbol rows (added by sase-1tz.2.1.6 commit 3d3d0f583d). The working tree resolves both symbols in doctor code (symvision: already properly used) and drops both rows locally. Re-keying was rejected: the symbols need no whitelist anywhere. Land agent: merge this stitch, then close this bead; the gate passes once the row removal lands.

## Dependencies

- **Depends on:** [sase-1tz.2.1.3](sase-1tz.2.1.3.md) ✓ · ⧖ 2026-11-19
- **Depends on:** [sase-1tz.2.1.6](sase-1tz.2.1.6.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.7/README.md) | [sase-1tz.2.1.7](sase-1tz.2.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`77c0f23`](https://github.com/sase-org/sase/commit/77c0f23375e70c2b684050a3267366f1e6dbdd40) | feat(doctor): group publication outbox by cause, settle terminal rows, calm stale-only protection | [sase-1tz.2.1.7](sase-1tz.2.1.7.md) | 2026-11-19 18:45:53 EST |

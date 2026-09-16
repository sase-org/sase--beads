# Bead: sase-11r.2 — Preserve worktree evidence on not-launchable follow-ups

[Bead Pages](../README.md) / [sase-11r](README.md) / sase-11r.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0lx](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0lx.md) · **Assignee:** `sase-11r.2` · **Size:** medium
**Created:** 2026-09-16 10:07:19 EDT · **Closed:** 2026-09-16 14:08:24 EDT
**Plan:** [202609/monitor\_verify\_handoff\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202609/monitor_verify_handoff_hardening.md)

## Description

recovery-evidence: snapshot the monitored workspace's uncommitted diff before claim release and add resume-command and snapshot hints to wait_checks notifications.

## Notes

[2026-09-16T18:07:41Z · sase-11r.2] PROPOSED FOLLOW-UP: Sudo canary acceptance test false positive — `test_sudo_local_flow_never_persists_canary_credentials` can fail when the credential length token appears in unrelated pending-action timestamps; direct rerun passed, so tighten the token check to avoid numeric coincidences.

[2026-09-16T18:08:24Z · sase-11r.2] Implemented monitor worktree recovery snapshots for not-launchable follow-ups, surfaced resume/snapshot hints in wait_checks notifications, added focused regression coverage, fixed shipped sase_questions skill-source contract drift, and verified with just fix, focused pytest coverage, generated skill/sudo reruns, and a final passing just check.

## Dependencies

- **Depends on:** [sase-11r.1](sase-11r.1.md) ✓ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11r.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11r.2/README.md) | [sase-11r.2](sase-11r.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb1e7f5`](https://github.com/sase-org/sase/commit/fb1e7f576b6c99a87a136094df9ce1b468e186fd) | fix(monitor): preserve recovery evidence for not-launchable follow-ups | [sase-11r.2](sase-11r.2.md) | 2026-09-16 14:29:12 EDT |

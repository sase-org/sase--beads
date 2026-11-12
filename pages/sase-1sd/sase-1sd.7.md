# Bead: sase-1sd.7 — Verify an existing attachments-private remote is actually private before pushing (sase-1db)

[Bead Pages](../README.md) / [sase-1sd](README.md) / sase-1sd.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bp](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bp.md) · **Assignee:** `sase-1sd.7` · **Size:** medium
**Created:** 2026-11-12 05:26:16 EST · **Closed:** 2026-11-12 18:31:04 EST
**Plan:** [202611/next\_seven\_salvage\_and\_unstrand.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_seven_salvage_and_unstrand.md)

## Description

private-remote-verify: preflight_sidecars compares visibility only when creating a missing attachments-private remote; an existing remote is trusted on its configured role alone and describe_label hard-codes "(private)", so attachment bytes can be pushed to a public repository under a private label. Probe visibility for existing remotes with resolve_remote_visibility at repo-init preflight and at the shared write boundary before the first upload per process, define honest unknown-visibility handling, and stop hard-coding the label.

## Notes

[2026-11-12T23:30:11Z · sase-1sd.7] TASK RESOLVED: sase-1db — existing attachments-private remotes are now probed with resolve_remote_visibility at repo-init preflight (src/sase/sdd/_sidecar_init.py: public refuses, unknown proceeds) and at the shared write boundary before the first upload per process (GitStoreWrites.put via _ensure_private_remote_not_public in src/sase/bead/attachments/git_store/writes.py); describe_label (src/sase/bead/attachments/upload/discovery.py) now derives its suffix from the probe — (private) / (private, unverified) / (PUBLIC — not private!) — instead of hard-coding (private). Doctor check already covered the anonymously-readable case. 10 new tests in tests/test_bead/test_attachment_private_remote_verify.py + 4 preflight tests green; neighboring suites green (public_store, git_attachment_store, upload, publish_lifecycle, sdd_store, doctor, repo-init handler).

[2026-11-12T23:30:32Z · sase-1sd.7] CHECK RESULT: sase tool run check (run 43b7f9c4342bc7a701d95d907eef1288): all lint stages green incl. symvision; test lane escalated to full suite — 60932 passed, 1 failed: tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_failed_row_dismiss_terminates_live_runner_and_stays_hidden. Base c77ff7e8f7. Before fix: repro showed preflight passing a public existing remote, describe_label claiming (private), put attempting push. After fix: all three refuse/alarm. The single failure is unrelated to this diff (ACE TUI runner dismissal; touches none of the changed files) and passes in isolation both on the clean base tree and with this diff applied (7s each) — load-induced flake under 19-minute full-lane contention (load1 ~30), not a regression.

[2026-11-12T23:30:45Z · sase-1sd.7] PROPOSED FOLLOW-UP: flake test_agents_tab_x_row_lifecycle_e2e.py::test_failed_row_dismiss_terminates_live_runner_and_stays_hidden under parallel/full-lane load (passes solo on base and with sase-1sd.7 diff; failed once in check run 43b7f9c4342bc7a701d95d907eef1288 with load1 ~30)

[2026-11-12T23:31:04Z · sase-1sd.7] Verified: existing public remotes refused at preflight and pre-upload put; labels probe-derived; focused + neighboring suites green; full check green except one proven load-flake (recorded). sase-1db work complete.

## Dependencies

- **Depends on:** [sase-1sd.6](sase-1sd.6.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sd.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.7/README.md) | [sase-1sd.7](sase-1sd.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`03b3a01`](https://github.com/sase-org/sase/commit/03b3a01dc9511cbf5be0f61f651894a90027e70f) | fix(attachments): refuse private bytes on public remotes | [sase-1sd.7](sase-1sd.7.md) | 2026-11-12 18:39:03 EST |

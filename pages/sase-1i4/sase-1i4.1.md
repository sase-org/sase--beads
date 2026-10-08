# Bead: sase-1i4.1 — Escape long-lived SASE helpers from the agent scope

[Bead Pages](../README.md) / [sase-1i4](README.md) / sase-1i4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5s.md) · **Assignee:** `sase-1i4.1` · **Size:** small
**Created:** 2026-10-08 06:37:33 EDT · **Closed:** 2026-10-08 06:52:28 EDT
**Plan:** [202610/agent\_scope\_leak\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_scope_leak_reaping.md)

## Description

escape-helpers: route the four fire-and-forget spawns reachable from an agent (background trash delete, goals fetch worker, federation worker daemon, tmux session bootstrap) through detach_scope so the new sweep can never kill them, with detach-scope worker tests.

## Notes

[2026-10-08T10:52:05Z · sase-1i4.1] PROPOSED FOLLOW-UP: symvision check gate reports 2 NEW unused symbols (context_block_texts in src/sase/instructions/muse.py, BeadStoreFingerprint in src/sase/core/bead_read_facade.py) that reproduce identically on the clean base tree

[2026-10-08T10:52:16Z · sase-1i4.1] PROPOSED FOLLOW-UP: tests/test_dispatch_federation.py IPC tests (test_ipc_client_decodes_success_and_error_frames, test_ipc_client_rejects_oversized_response) fail on thread-ready timeout identically on the clean base tree

[2026-10-08T10:52:28Z · sase-1i4.1] Routed all four fire-and-forget spawns through detach_scope (trash delete sase-trash-delete, goal fetch sase-goal-fetch via shared spawn_fetch_worker, federation worker sase-federation, tmux bootstrap sase-tmux with start_new_session plumbed through run_tmux_command); extended tests/test_detach_scope_background_workers.py with 9 tests (escaped+noop per site plus fast-path delegation), 17/17 pass. just check: all lint gates pass except symvision 2 NEW items that reproduce on clean base (noted as follow-ups); neighbor suites pass except 2 pre-existing IPC failures also reproduced on clean base.

## Dependencies

- **Blocks:** [sase-1i4.2](sase-1i4.2.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1i4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1i4.1/README.md) | [sase-1i4.1](sase-1i4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`dbf6357`](https://github.com/sase-org/sase/commit/dbf6357464fc9a27b947c26cd8fb50fb06c02486) | feat(detach): route background workers through detach\_scope | [sase-1i4.1](sase-1i4.1.md) | 2026-10-08 06:54:11 EDT |

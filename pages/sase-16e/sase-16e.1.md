# Bead: sase-16e.1 — Durable rescue store and non-refusing sidecar eviction

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.1` · **Size:** medium
**Created:** 2026-09-22 12:13:29 EDT · **Closed:** 2026-09-22 14:41:35 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

rescue-store: add a best-effort rescue store outside the workspace (git bundles, worktree patches, manifests, retention, one notification per rescue) and change launch-time sidecar protection to publish once, rescue, and always proceed with eviction instead of raising _WorkspaceBeadEvictionRefused.

## Notes

[2026-09-22T18:39:44Z · sase-16e.1] PROPOSED FOLLOW-UP: test_commit_bead_hooks.TestHandleBeads 3 failures (bead sync subprocess mock expects no env kwarg, actual passes env=None) fail on pristine master too — needs owner triage

[2026-09-22T18:40:42Z · sase-16e.1] PROPOSED FOLLOW-UP: test_every_bead_free_text_option_is_classified fails on pristine master (unclassified read/project, read/reason, touched/verb) — needs owner triage

[2026-09-22T18:41:35Z · sase-16e.1] rescue-store done: new workspace_provider/rescue.py (bundle+patch+manifest, retention, one workspace-rescue notification); launch eviction publishes once (30s lock wait, memo by repo+HEAD), rescues, always proceeds; _WorkspaceBeadEvictionRefused deleted; docs updated. Verified: 31 focused tests pass (rescue, eviction, auto-connect) + 4 prepare-regression pass; just check 7281 passed with only 4 pre-existing failures (3 commit-hooks env=None, 1 free-text classification — each reproduced on pristine master, filed as PROPOSED FOLLOW-UP notes)

## Dependencies

- **Blocks:** [sase-16e.2](sase-16e.2.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.1/README.md) | [sase-16e.1](sase-16e.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f42a6f9`](https://github.com/sase-org/sase/commit/f42a6f964af6ab0cfaf22dca5115585b92d966c4) | feat(workspace): durable rescue store and non-refusing sidecar eviction | [sase-16e.1](sase-16e.1.md) | 2026-09-22 14:44:03 EDT |

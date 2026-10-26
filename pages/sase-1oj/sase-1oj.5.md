# Bead: sase-1oj.5 — Stop per-launch Codex thread backfill

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.5` · **Size:** medium
**Created:** 2026-10-26 16:07:29 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Description

codex-private-sessions: give each shadow CODEX_HOME a private sessions tree whose today/tomorrow day dirs link to the real rollout store. Rescue stray rollouts at teardown, sweep orphaned shadow homes safely, and update the Codex provider docs.

## Notes

[2026-10-26T21:17:41Z · sase-1oj.5] Live probe (codex exec --json, trivial prompt, -C /tmp): sessions/ is a real dir; state_5.sqlite=278528 bytes (~0.27 MB vs 347 MB baseline); session_meta first rollout line at 2026-10-26T21:09:31.529Z (~0.7s after filename 21:09:30); rollout landed at ~/.codex/sessions/2026/10/26/rollout-2026-10-26T21-09-30-01a17a0c-0641-78d3-bfa6-6794b34feb80.jsonl; shadow home removed after teardown. Codex stderr included "failed to record rollout items: thread not found" with exit 0; rollout still contains the full session. Tests: 32 passed (private sessions + shadow home + dir-op audit). No feature flag: old sessions symlink was an implementation detail; SASE_CODEX_DISABLE_SHADOW_HOME=1 remains.

[2026-10-26T22:28:39Z · sase-1oj.5--1] Recovery: discovery test now uses monkeypatched dates; 32 targeted tests passed (private sessions + shadow home + dir-op audit); just fix clean. Previous just check timed out after fmt on model-policy under load1~10-20; re-running just check for host completion.

## Dependencies

- **Blocks:** [sase-1oj.6](sase-1oj.6.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.5.md) | [sase-1oj.5](sase-1oj.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d6d8b2b`](https://github.com/sase-org/sase/commit/d6d8b2b9425ae2c4e88aa689ad8a89c03852732b) | feat(codex): isolate shadow-home sessions to today and tomorrow | [sase-1oj.5](sase-1oj.5.md) | 2026-10-26 19:48:02 EDT |

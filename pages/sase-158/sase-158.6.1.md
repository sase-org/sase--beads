# Bead: sase-158.6.1 — Bound streaming waits, fix CRLF, and fix backend step details

[Bead Pages](../README.md) / [sase-158.6](sase-158.6.md) / sase-158.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-158.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-158.land.md) · **Assignee:** `sase-158.6.1` · **Size:** small
**Created:** 2026-09-21 16:18:57 EDT · **Closed:** 2026-09-21 17:38:35 EDT
**Plan:** [202609/sase\_update\_live\_progress\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_update_live_progress_fixes.md)

## Description

stream-and-backend-fixes: always group-kill and bound the pump joins in run_streaming (enforcing timeouts after leader exit), keep CRLF lines, isolate prebuild stdin, parent the health-check repair row, clear stale transient merge details, and regenerate the stale completion snapshot.

## Notes

[2026-09-21T21:37:18Z · sase-158.6.1] PROPOSED FOLLOW-UP: pre-existing failures outside this phase need owners — session_proc_reporter uv on_output fake mismatch, 2 snippet rich-format tests, notify help test, plus TUI bench/visual/llm/machine_init/bead-cli failures seen in just check

[2026-09-21T21:38:35Z · sase-158.6.1] stream_command: always group-SIGKILL + bounded (~2s) daemon pump joins, post-leader-exit deadline enforced as TimeoutExpired, same kill on KI path; CRLF strip-one-then-collapse; prebuild stdin=DEVNULL; repair row declared parented; merge done falls back to fast-forwarded detail; cli_spec.json regenerated (only -v/--verbose + digest drift). Verified: 31 stream/progress tests, 409 dev_update+completion, 2331 update_progress/mode_switch/main pass; lint+fmt+mypy clean via just check; remaining full-check failures proven pre-existing via stash

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-158.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-158.6.1/README.md) | [sase-158.6.1](sase-158.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0ffcfd`](https://github.com/sase-org/sase/commit/e0ffcfde81bc681f3942d00cee34e9b9fdec6c35) | fix(dev-update): bound streaming waits, CRLF lines, and backend step details | [sase-158.6.1](sase-158.6.1.md) | 2026-09-21 17:40:36 EDT |

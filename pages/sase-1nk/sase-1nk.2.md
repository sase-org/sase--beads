# Bead: sase-1nk.2 — Restore the host PATH for agent launches made from agent shells

[Bead Pages](../README.md) / [sase-1nk](README.md) / sase-1nk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.133](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.133.md) · **Assignee:** `sase-1nk.2` · **Size:** medium
**Created:** 2026-10-23 09:29:10 EDT · **Closed:** 2026-10-23 10:04:20 EDT
**Plan:** [202610/monitor\_followup\_output\_and\_host\_path.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_followup_output_and_host_path.md)

## Description

host-path-launch-env: runners stamp a SASE_HOST_PATH_SNAPSHOT of their PATH and spawn_agent_subprocess restores it, so login-shell PATH resets cannot hide provider CLIs.

## Notes

[2026-10-23T14:04:07Z · sase-1nk.2] PROPOSED FOLLOW-UP: Clean-base TUI import budget (sase-1ic) — just check failed at 3529 modules against the strict 3527 cap; the exact import-budget test reproduced on clean base while phase changes were stashed.

[2026-10-23T14:04:20Z · sase-1nk.2] Implemented runner PATH snapshots and host-first, deduplicated restoration for nested agent launches; explicit extra_env PATH still wins, absent snapshots leave PATH unchanged, and monitored-command PATH remains untouched per decision. Focused current-tree verification passed (29 tests). just check ran 57,185 passed and 3 failed: the terminology failure from the initial docs wording was fixed and now passes; TUI import budget reproduces on clean base at 3529 vs 3527 and is recorded against existing sase-1ic; the Grok probe failure passed on focused clean-base rerun. Required epic-symbol check found no entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nk.2/README.md) | [sase-1nk.2](sase-1nk.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ed321c5`](https://github.com/sase-org/sase/commit/ed321c5434bba31c7636bdc8dadc80afba040a7f) | fix(agent-launch): restore host PATH for nested launches | [sase-1nk.2](sase-1nk.2.md) | 2026-10-23 10:05:29 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nk.2][1] | Need the phase scope, design file, and prior work notes before implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nk.2/README.md

<!-- sase:referenced-by:end -->

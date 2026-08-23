# Bead: sase-s6.5 — Native stand-alone proc runtime

[Bead Pages](../README.md) / [sase-s6](README.md) / sase-s6.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0b8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0b8.md) · **Assignee:** `sase-s6.5` · **Size:** medium
**Created:** 2026-08-22 14:14:59 EDT · **Closed:** 2026-08-22 19:42:12 EDT
**Plan:** [202608/typed\_launch\_units.md](https://github.com/sase-org/sase--plans/blob/main/202608/typed_launch_units.md)

## Description

standalone-proc-runtime: dispatch %proc units through native proc-shell identity, deferred operational workspaces, private scripts, sanitized environments, responsive cancellation, and crash-safe settlement.

## Notes

[2026-08-22T23:41:47Z · sase-s6.5] PROPOSED FOLLOW-UP: just rust-install leaves .venv/bin/sase-xprompt-lsp stale — ACE/LSP directive recipe parity fails until rust-dev-install rebuilds the LSP binary from the same sase-core checkout.

[2026-08-22T23:42:12Z · sase-s6.5] Implemented native %proc dispatch: xprompt-proc proc-shell reservation after admission, supervisor lease/script/settlement-before-ack, private 0600 scripts, sanitized env, argv without interpolation, cancel, fingerprint replay. Verified cargo test/clippy sase_core, pytest tests/test_launch_proc_runtime.py plus admission/condition/proc runner, just check (lint+scoped; prior full-suite escalation 36169 passed after rebuilding sase-xprompt-lsp). No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-s6.3](sase-s6.3.md) ✓ · ⧖ 2026-08-22
- **Depends on:** [sase-s6.4](sase-s6.4.md) ✓ · ⧖ 2026-08-22
- **Blocks:** [sase-s6.7](sase-s6.7.md) ✓ · ⧖ 2026-08-22
- **Blocks:** [sase-s6.8](sase-s6.8.md) ✓ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s6.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s6.5/README.md) | [sase-s6.5](sase-s6.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f00bec`](https://github.com/sase-org/sase/commit/0f00becd749b533f850bf4a81d1cccbefe35b792) | feat(agent-launch): dispatch stand-alone %proc units natively | [sase-s6.5](sase-s6.5.md) | 2026-08-22 19:44:30 EDT |
| sase-core | [`sase-core@92a4fc4`](https://github.com/sase-org/sase-core/commit/92a4fc4bff40dad7e9960617da2df72a1fbf5807) | feat(agent-launch): add native %proc dispatch helpers | [sase-s6.5](sase-s6.5.md) | 2026-08-22 19:46:43 EDT |

# Bead: sase-ix.5.1 — Fall back safely for malformed observation metadata

[Bead Pages](../README.md) / [sase-ix.5](sase-ix.5.md) / sase-ix.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ix.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.land/README.md) · **Assignee:** `sase-ix.5.1` · **Size:** small
**Created:** 2026-08-10 13:27:13 EDT · **Closed:** 2026-08-10 13:44:02 EDT
**Plan:** [202608/finish\_plus\_one\_reopen\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_plus_one_reopen_landing.md)

## Description

harden-observation-metadata: validate agent_meta.json run_started_at before passing it to the Rust +1 mutation, fall back to a sub-second current instant with a debug diagnostic when it is malformed, and add direct and CLI regressions.

## Notes

[2026-08-10T17:44:02Z · sase-ix.5.1] Added _is_rfc3339_instant validation in identity.py so resolve_observation_window_start falls back to current_instant() with a debug log when agent_meta.json's run_started_at is malformed; added tests/agent/test_identity.py (23 direct unit cases) and a CLI regression in tests/test_bead/test_cli_plus_one.py covering the malformed-metadata plus-one reopen path. just install, focused pytest (23 passed), and just check (all lint gates + full escalated test suite) all passed.

## Dependencies

- **Blocks:** [sase-ix.5.2](sase-ix.5.2.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ix.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ix.5.1/README.md) | [sase-ix.5.1](sase-ix.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2f2624`](https://github.com/sase-org/sase/commit/f2f26245e59341888323420b71d69888b38c0f6b) | fix(identity): fall back safely on malformed observation metadata | [sase-ix.5.1](sase-ix.5.1.md) | 2026-08-10 13:45:09 EDT |

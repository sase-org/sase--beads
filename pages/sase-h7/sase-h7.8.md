# Bead: sase-h7.8 — Mobile wire and Telegram step flow for declared inputs

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.8` · **Size:** large
**Created:** 2026-08-07 17:08:08 EDT · **Closed:** 2026-08-07 20:49:05 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Previously Closed

> ↺ Closed 2026-08-07T23:30:53Z · done
>
> (none)
>
> Reopened 2026-08-07T23:32:34Z by `sase bead open`

> ↺ Closed 2026-08-07T23:07:03Z · done
>
> (none)
>
> Reopened 2026-08-07T23:09:35Z by `sase bead open`

## Description

inputs-remote: extend the frozen `mobile_api_v1` gate contract in `sase-core` with declared input fields and per-option submitted values, update the Rust request struct, routes, and Python bridge, and add an input step flow to the Telegram gate conversation.

## Notes

[2026-08-08T00:49:05Z · sase-h7.8] Implemented sections 1-6 of 202608/gate_inputs_telegram.md in sase-telegram: GateProgress input fields, new gate_inputs.py step-flow module, formatting.py prompt/keyboard, inbound.py option_inputs plumbing, sase_tg_inbound.py step-flow wiring, and deletion of feedback_is_command_input. Verified in sase-telegram: ruff+mypy clean, pytest 545 passed / 9 failed (pre-existing presentation.title failures from ff0b765a4, confirmed via git stash to exist on master without this change). sase workspace unchanged, no verification needed there.

## Dependencies

- **Blocks:** [sase-h7.11](sase-h7.11.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.2](sase-h7.2.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.3](sase-h7.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-h7.8.md) | [sase-h7.8](sase-h7.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@65e0ec1`](https://github.com/sase-org/sase-core/commit/65e0ec1e7323fc1ca958e7dabe806acc6661bd96) | feat(mobile)!: carry declared gate inputs on the mobile wire | [sase-h7.8](sase-h7.8.md) | 2026-08-07 19:08:56 EDT |
| sase | [`7bbd82a`](https://github.com/sase-org/sase/commit/7bbd82a47ed7b3e2aec55ec0dfce76ed128f1cb5) | feat(mobile): accept per-option gate inputs on the mobile bridge | [sase-h7.8](sase-h7.8.md) | 2026-08-07 19:31:45 EDT |

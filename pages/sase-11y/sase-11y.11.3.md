# Bead: sase-11y.11.3 — Rewrite the docs that still describe the pre-host model

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.3` · **Size:** small
**Created:** 2026-09-21 07:19:32 EDT · **Closed:** 2026-09-21 09:46:29 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

stale-docs: rewrite the Telegram receiver paragraph in `notifications.md` for the `telegram_receiver` service proc, and drop the removed `service_host` flag from three blog posts. Fix the `chat_install.restart_attempts` schema description. Point the mobile runbook at `sase service proc restart gateway`. Align the ACE and plugin docs with the relabeled restart option.

## Notes

[2026-09-21T13:45:12Z · sase-11y.11.3] PROPOSED FOLLOW-UP: just check mypy gate fails on untouched src/sase/dev_update/prebuild.py (arg-type at lines 134/162, _run_command vs DevCommandRunner) — pre-existing, unrelated to stale-docs

[2026-09-21T13:46:29Z · sase-11y.11.3] Rewrote Telegram receiver paragraph for telegram_receiver service proc (verified against sase-telegram default_config.yml/receiver.py; kept sase-11w ref since still open); dropped service_host flag clauses from 3 blog posts; aligned chat_install.restart_attempts schema description with configuration.md; added sase service proc restart gateway to mobile runbook; aligned ace.md Q-menu with relabeled restart wording. just fix clean; 67 related tests pass (chat_install, gate preview, config schema, markdown width); no epic-symbols. just check blocked by pre-existing mypy error in untouched prebuild.py (noted as follow-up).

## Dependencies

- **Depends on:** [sase-11y.11.2](sase-11y.11.2.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.3/README.md) | [sase-11y.11.3](sase-11y.11.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`420d72b`](https://github.com/sase-org/sase/commit/420d72bb1d230a8697ec344a24bd0d07a36bb8df) | docs(sase-11y): rewrite pre-host leftovers for service-host model | [sase-11y.11.3](sase-11y.11.3.md) | 2026-09-21 09:48:46 EDT |

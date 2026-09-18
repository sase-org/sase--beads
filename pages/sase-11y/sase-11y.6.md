# Bead: sase-11y.6 — Gateway builtin and Telegram plugin migration

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.6` · **Size:** large
**Created:** 2026-09-16 14:42:03 EDT · **Closed:** 2026-09-18 07:34:00 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

gateway-telegram: add the gateway builtin launcher and sase mobile gateway pair, default the gateway off in core config, and migrate the sase-telegram receiver to a plugin-declared service proc while retiring the rearm tick and core's origin-string hack.

## Notes

[2026-09-18T11:34:00Z · sase-11y.6] Implemented the gateway and Telegram service-host migration. Verified main just check and sase-telegram just check; gateway start now delegates to the service host when enabled, pairing is explicit through mobile gateway pair, the host owns direct gateway builtin launch, and the Telegram receiver defers to its configured service proc under service_host.

## Dependencies

- **Depends on:** [sase-11y.4](sase-11y.4.md) ✓ · ⧖ 2026-09-16
- **Blocks:** [sase-11y.9](sase-11y.9.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.6.md) | [sase-11y.6](sase-11y.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e92e6c9`](https://github.com/sase-org/sase/commit/e92e6c91c1ed4f8ff8d8f83250674d7dd46dbf61) | feat(mobile): move gateway to service host | [sase-11y.6](sase-11y.6.md) | 2026-09-18 07:49:43 EDT |
| sase-telegram | [`sase-telegram@2f76876`](https://github.com/sase-org/sase-telegram/commit/2f768762d2aba05cafa52ba7a7ec96d71a4342d9) | feat(receiver): register service-host proc | [sase-11y.6](sase-11y.6.md) | 2026-09-18 07:54:07 EDT |

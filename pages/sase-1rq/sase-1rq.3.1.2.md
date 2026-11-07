# Bead: sase-1rq.3.1.2 — Fix the known macOS-only test failures and the Google sign-in hang

[Bead Pages](../README.md) / [sase-1rq.3.1](sase-1rq.3.1.md) / sase-1rq.3.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.3.md) · **Assignee:** `sase-1rq.3.1.2` · **Size:** medium
**Created:** 2026-11-07 08:10:12 EST
**Plan:** [202611/bob\_cli\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/bob_cli_ci_green.md)

## Description

mac-known-failures: on the mac host, reproduce and fix the macOS-only failures already seen in CI. Lib: one case-insensitive-APFS test and three /var vs /private/var path tests. CLI: clipboard_status picking Alfred over the command provider. gcal_auth: 11 login tests each stall about 600 s because choose_flow picks the browser flow on macOS, so the paste-scripted tests wait out CONSENT_WINDOW. Make every Google login test family (gcal_auth, gmail_shell, and gkeep_auth if affected) select its flow deterministically on every OS.

## Dependencies

- **Blocks:** [sase-1rq.3.1.3](sase-1rq.3.1.3.md) ◐ · ⧖ 2026-11-07
- **Blocks:** [sase-1rq.3.1.4](sase-1rq.3.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.3.1.2/README.md) | [sase-1rq.3.1.2](sase-1rq.3.1.2.md) | 0 |

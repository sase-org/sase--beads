# Bead: sase-f2.2 — Prompt archive publishes only the verbatim body

[Bead Pages](../README.md) / [sase-f2](README.md) / sase-f2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ej.land.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.land.w2/README.md) · **Assignee:** `sase-f2.2` · **Size:** medium
**Created:** 2026-08-03 14:48:31 EDT · **Closed:** 2026-08-03 15:14:07 EDT
**Plan:** [202608/revert\_stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_stored_prompt_duality.md)

## Description

archive: remove the appended rendered-prompt section and the xprompt link rewrite from prompt archive rendering and preparation, drop the sentinel/fence/link-target checks and the legacy counter from validation, and restore the sidecar agents README template.

## Notes

[2026-08-03T19:13:15Z · sase-f2.2] PROPOSED FOLLOW-UP: reconcile unrelated ACE Config Center visual/check failures — just check failed after archive changes on two Agent CLI Config Center PNG snapshots whose actual output includes an Update history panel missing from goldens, and one stall-watchdog test that passed on direct rerun.

[2026-08-03T19:14:07Z · sase-f2.2] Removed rendered/xprompt prompt archive output and validation paths; verified focused archive/CLI tests pass, stale archive symbols are absent, sase init repo --check is clean, and just check ran through lint/validation but hit unrelated ACE Config Center visual snapshot drift noted as PROPOSED FOLLOW-UP.

[2026-08-03T19:15:43Z · sase-f2.2] Verified closed after archive tests, init check, scoped diff review, and finalizer status check.

## Dependencies

- **Blocks:** [sase-f2.3](sase-f2.3.md) ◐
- **Blocks:** [sase-f2.4](sase-f2.4.md) ◐
- **Blocks:** [sase-f2.6](sase-f2.6.md) ◐

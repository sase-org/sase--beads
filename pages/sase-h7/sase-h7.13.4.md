# Bead: sase-h7.13.4 — Assert the mobile leg the epic shipped

[Bead Pages](../README.md) / [sase-h7.13](sase-h7.13.md) / sase-h7.13.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.land/README.md) · **Assignee:** `sase-h7.13.4` · **Size:** medium
**Created:** 2026-08-07 23:12:31 EDT · **Closed:** 2026-08-07 23:48:11 EDT
**Plan:** [202608/gate\_inputs\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_inputs_landing.md)

## Description

mobile-conformance: declare the per-option input capability the mobile bridge actually has, submit it through the conformance driver, and replace the stale closed-phase excuses on whatever the bridge still cannot do with an honest reason or the missing support.

## Notes

[2026-08-08T03:48:57Z · sase-h7.13.4] Declared CAP_OPTION_INPUTS on the mobile surface and threaded submission.option_inputs through _submit_via_mobile into execute_mobile_gate_action; the 7 previously-skipped option_inputs cases now assert and pass with no bridge divergence from CLI/ACE (secret redaction and schema_validation_failed error records included). Kept shared_input and retry unsupported (the bridge wire carries neither field; adding them needs a wire schema bump synchronized with the Rust gateway) and replaced their stale 'sase-h7.8 (inputs-remote)' excuses with the real limitation plus the CLI/ACE workaround. Added test_every_surface_gap_states_why_it_cannot_submit, which fails if a deferral names a bead, outlives the capability, or is missing for a real gap. Corrected docs/mobile_gateway.md's false 'omitted fields fall back to the declared default' claim (optional_scalar_omitted asserts the opposite) and documented both mobile gaps. Verified: tests/gate_conformance 40 passed / 3 skipped (was 29 passed / 13 skipped), tests/test_mobile_gate_option_inputs.py + tests/test_mobile_notifications_bridge.py green, and 'just check' exit 0 with every lint gate passing.

[2026-08-08T03:49:56Z · sase-h7.13.4] Correction to the close note's counts: tests/gate_conformance went from 32 passed / 10 skipped to 40 passed / 3 skipped (42 matrix cases plus the new guard test); the remaining 3 skips are mobile shared_input and the two mobile retry cases.

## Dependencies

- **Depends on:** [sase-h7.13.1](sase-h7.13.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.13.5](sase-h7.13.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.13.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.13.4/README.md) | [sase-h7.13.4](sase-h7.13.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`86a54a6`](https://github.com/sase-org/sase/commit/86a54a674ca14ae3313602b26af3bc9e2022bc39) | test(gate): assert the mobile leg the gate-input epic shipped | [sase-h7.13.4](sase-h7.13.4.md) | 2026-08-07 23:48:29 EDT |

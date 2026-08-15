# Bead: sase-m9.2.1.6.2 — Require the published proc lifecycle bindings

[Bead Pages](../README.md) / [sase-m9.2.1.6](sase-m9.2.1.6.md) / sase-m9.2.1.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.2.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.2.1.land.md) · **Assignee:** `sase-m9.2.1.6.2` · **Size:** small
**Created:** 2026-08-15 10:21:12 EDT · **Closed:** 2026-08-15 11:24:18 EDT
**Plan:** [202608/finish\_unified\_proc\_shell\_platform.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_unified_proc_shell_platform.md)

## Description

integrate-published-core-floor: raise the sase-core-rs dependency floor from 0.27.2 to the first published release containing reserve_proc, claim_proc_supervisor, request_proc_stop, begin_proc_settlement, and finish_proc (phase notes identify 0.27.3), retain the <0.28.0 ceiling, and refresh uv.lock against published packages rather than relying on the linked editable 0.27.4 checkout. Verify the core-floor probe, binding validation, package metadata, and Python wire/facade tests against the declared minimum. Audit all schema-v3 capabilities used by the Python proc service so the floor covers the complete runtime API, not only importable names. Run just install and just check. Record unrelated failures as PROPOSED FOLLOW-UP on this phase.

## Notes

[2026-08-15T14:38:06Z · sase-m9.2.1.6.2] Raised sase-core-rs floor to 0.27.4 (0.27.3 is first lifecycle release but lacks query-profile bindings this tree already requires). Added schema-v3 proc lifecycle bindings and behavioral probe. Verified published 0.27.4 wheel: bindings 303/303, validate_sase_core_rs, facade tests. just check escalated to full suite; handing off.

[2026-08-15T15:23:11Z · sase-m9.2.1.6.2] PROPOSED FOLLOW-UP: Full-suite settlement recovery flake - just check escalated due packaging-config and failed tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash once; focused rerun passed.

[2026-08-15T15:24:18Z · sase-m9.2.1.6.2] Raised sase-core-rs floor to 0.27.4,<0.28.0 and refreshed uv.lock. Added validate_sase_core_rs required lifecycle bindings plus schema-v3 reserve/claim/stop/settle/finish behavioral probe and tests. Verified: just install; tools/check_sase_core_rs_bindings (303/303); tools/validate_sase_core_rs; tools/probe_core_floor against published floor; pytest tests/test_validate_sase_core_rs_tool.py tests/test_procs_facade.py; package metadata reports sase-core-rs 0.27.4 and reserve_proc/finish_proc present; scratch 0.27.3 check fails missing four query-profile bindings, confirming 0.27.4 floor. just check passed lint/validation gates but escalated to full suite and failed once in unrelated tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash; focused rerun passed and PROPOSED FOLLOW-UP recorded.

[2026-08-15T15:27:06Z · sase-m9.2.1.6.2] Verified dependency floor raised to sase-core-rs 0.27.4, lifecycle binding validator probe and tests pass, targeted facade tests pass, and just check completed all gates except one unrelated settlement recovery test that passed on focused rerun and was recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-m9.2.1.6.3](sase-m9.2.1.6.3.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.2.1.6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.2.1.6.2/README.md) | [sase-m9.2.1.6.2](sase-m9.2.1.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ca93686`](https://github.com/sase-org/sase/commit/ca93686a65d1ad53ecf1c94d024658750f05bb27) | build(deps): require proc lifecycle core bindings | [sase-m9.2.1.6.2](sase-m9.2.1.6.2.md) | 2026-08-15 11:28:02 EDT |

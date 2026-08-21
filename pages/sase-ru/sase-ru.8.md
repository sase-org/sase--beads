# Bead: sase-ru.8 — Make EpicResume gating unconditional

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.8` · **Size:** small
**Created:** 2026-08-21 10:44:30 EDT · **Closed:** 2026-08-21 12:13:06 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

epic_resume_retirement: remove epic_resume_gate after its operational evidence passes while preserving settle-window, deduplication, cancellation, and retry safeguards.

## Notes

[2026-08-21T16:11:08Z · sase-ru.8] PROPOSED FOLLOW-UP: just check lint(ruff) F601 — duplicate dict key sase_finalizer in src/sase/telemetry/catalog.py:17 and :25 from concurrent telemetry/finalizer work; blocks just check before later gates

[2026-08-21T16:11:31Z · sase-ru.8] PROPOSED FOLLOW-UP: tools/check_feature_flags rule 7 fails on closed sase-qe still owning coder_inherits_planner_chat (concurrent planner-chat retirement); rule 8 still fails on out-of-scope sase-rc artifact_links

[2026-08-21T16:12:00Z · sase-ru.8] PROPOSED FOLLOW-UP: ACE config pane tests query ConfigPane at #config but the widget is now ConfigHubPane — concurrent TUI work, ~30 failures in test_config_pane_widget*.py

[2026-08-21T16:12:29Z · sase-ru.8] PROPOSED FOLLOW-UP: escalated full suite also failed occupancy tests (sase-core 0.29.6), missing sase-xprompt-lsp, completion snapshot field-order drift, and contract_manifest 53>52 — none caused by epic_resume_gate retirement

[2026-08-21T16:13:06Z · sase-ru.8] Made EpicResume gating unconditional: deleted the flag_disabled early return, retired epic_resume_gate from registry/schema/help/docs, closed sase-qh. Soak sase-ru.3 evidence: one gate per settled stall; settle/handoff/fast-retry/recovery-before-settle produce no false positives; resume_argv is sase bead work. Preserved settle window, fingerprint dedup, recovery cancellation, fail-closed inventory/scan, and notification priority. Focused chop/soak/gate/stall-policy/schema tests: 82 passed. just check blocked by unrelated ruff F601; escalated full suite 35622 passed / 64 failed, all failures unrelated. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21
- **Depends on:** [sase-ru.3](sase-ru.3.md) ✓ · ⧖ 2026-08-21

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cf53a17`](https://github.com/sase-org/sase/commit/cf53a17ad727fa9b27d8b8ba8c1ad6ccbee75317) | feat: Make EpicResume gating unconditional (sase-ru.8) | [sase-ru.8](sase-ru.8.md) | 2026-08-21 12:17:34 EDT |

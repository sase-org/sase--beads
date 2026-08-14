# Bead: sase-l3.8 — Authenticated end-to-end smoke exercises

[Bead Pages](../README.md) / [sase-l3](README.md) / sase-l3.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zu](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zu.md) · **Assignee:** `sase-l3.8` · **Size:** xsmall
**Created:** 2026-08-13 14:44:43 EDT · **Closed:** 2026-08-13 20:22:52 EDT
**Plan:** [202608/grok\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/grok_provider.md)

## Description

smoke: launch real SASE agents on the grok provider to confirm text, reasoning, tool rows, usage, skills, interrupt/relaunch, and failure diagnostics behave in ACE.

## Notes

[2026-08-13T23:14:51Z · sase-l3.8] PROPOSED FOLLOW-UP: Monitor start fails for dotted phase-agent names — `sase monitor start` from agent `sase-l3.8` raises FamilyAttachError: Cannot create agent family `sase-l3`; resolved parent is named `sase-l3.8`, blocking the plan-required monitored `just check-full` handoff.

[2026-08-14T00:00:08Z · sase-l3.8] PROPOSED FOLLOW-UP: Linked Rust core/Python wire mismatch breaks `just check-full` task and notification lanes — after `just install`, `sase-core-rs 0.27.0` returns task wire schema 2 while Python expects 1, and Rust notification state updates reject `mark_tab_read`; representative failures: `tests/test_tasks_facade.py::test_rust_facade_round_trip_update_and_get` and `tests/notification_store/test_state_updates.py::TestMarkTabRead::test_marks_only_targeted_tab`.

[2026-08-14T00:22:52Z · sase-l3.8] Verified Grok smoke: live ACE agents grok-smoke-no-tool, grok-smoke-tools, and grok-smoke-bad-model confirmed provider/model labeling, response text, nonzero usage, Grok thinking records, runtime=grok tool rows with command/path/exit-code detail, native sase_var skill use with /tmp no-sandbox write, and errors[] invalid-model diagnostics. Live interrupt run exposed reusable provider_timer failure; fixed in src/sase/llm_provider/grok.py, added regression coverage, and verified with direct workspace GrokProvider interrupt/relaunch producing interrupt_log.jsonl and GROK_INTERRUPT_RESUMED. Focused Grok tests passed; just check/check-full remain blocked by recorded unrelated linked-core wire mismatch, and monitored check handoff is blocked by recorded dotted phase-agent monitor bug.

[2026-08-14T00:23:28Z · sase-l3.8] Verified live Grok ACE smoke runs for no-tool text, usage, reasoning, tool rows, native skill/tool execution, bad-model diagnostics, doctor present/missing diagnostics; fixed and directly verified Grok interrupt relaunch; focused Grok tests passed. just check/full remain blocked by unrelated linked-core wire mismatch recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-l3.7](sase-l3.7.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-l3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-l3.8/README.md) | [sase-l3.8](sase-l3.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aef2d8e`](https://github.com/sase-org/sase/commit/aef2d8eb5b11c46265a468fa49686c52d33cb79a) | fix(grok): recreate timer for interrupt relaunch | [sase-l3.8](sase-l3.8.md) | 2026-08-13 20:24:14 EDT |

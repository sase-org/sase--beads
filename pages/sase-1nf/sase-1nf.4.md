# Bead: sase-1nf.4 — Lossless EpicFollowView encoding for bundles and cleanup payloads

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.4` · **Size:** medium
**Created:** 2026-10-20 13:36:14 EDT · **Closed:** 2026-10-20 14:04:46 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

cleanup-encoding: encode wait_epic_follows explicitly in the shared agent bundle encoder, decode it back into EpicFollowView, guard against the next non-JSON field, and make the cleanup test harness round-trip payloads through JSON. Closes sase-1nb.

## Notes

[2026-10-20T18:04:46Z · sase-1nf.4] cleanup-encoding done: shared bundle encoder projects wait_epic_follows to plain dicts (ten fields, tuples as lists) with lazy epic_follow_views decode-back; cleanup harness round-trips AGENT_CLEANUP payloads through JSON; guard + round-trip + dismiss + bulk-kill tests added; sase tool run check verdict pass; no epic-symbol leftovers; sase-1nb closed with evidence.

[2026-10-23T13:14:10Z · sase-1nf.4] CLOSED-BEAD LAUNCH: agent sase-1nf.4 launched against this closed bead; status left closed.
Launch submitted 2026-10-23T13:12:58.875948Z; run 20261023091259.
Prior close: 2026-10-20T18:04:46Z · done.

[2026-10-23T13:19:07Z · sase-1nf.4] REVERIFIED 2026-10-23: Earlier work landed in 682e52fc716fd93a1481abbad57a9f219c6877a1, an ancestor of clean HEAD 92d271364cb5a8c20293c0a9707a31db04b6d429. Reviewed the approved cleanup-encoding design and current implementation; the encoder, lazy decoder, JSON cleanup harness, and regressions remain present and unchanged since that commit. Ran .venv/bin/python -m pytest -q tests/test_agent_model_bundle.py tests/ace/tui/actions/test_cleanup_payload.py tests/ace/tui/test_app_import_budget.py: all 44 bundle/cleanup tests passed, including all ten EpicFollowView fields, empty and populated states, archive JSON round-trip, dismiss, and bulk kill. The deferred-module assertion passed. Only the existing whole-app import-count budget failed; see separate PROPOSED FOLLOW-UP. No code changes or reopening needed.

[2026-10-23T13:19:22Z · sase-1nf.4] PROPOSED FOLLOW-UP: Existing TUI startup import-budget failure, tracked by sase-1ic — On unchanged clean HEAD 92d271364cb5a8c20293c0a9707a31db04b6d429, tests/ace/tui/test_app_import_budget.py::test_tui_app_import_stays_under_startup_budget fails with 3529 modules against strict cap 3527. Reproduced identically both in the 44-pass bundle/cleanup run and with .venv/bin/python -m pytest -q --tb=short tests/ace/tui/test_app_import_budget.py. git diff --exit-code HEAD was clean before the isolated reproduction; this run made no code changes. The deferred-module assertion, including sase.core.wait_epic_follow_view, passes. sase-1ic already contains identical 3529/3527 clean-base evidence from 2026-10-21. Leave triage with the epic land agent; this pre-existing failure does not reopen the completed cleanup-encoding phase.

[2026-10-23T13:19:34Z · sase-1nf.4] Verified existing commit 682e52fc71 is in HEAD; all 44 bundle/cleanup regressions pass; no epic-symbol entries. Pre-existing startup import-budget failure reproduced on clean base and recorded as PROPOSED FOLLOW-UP citing sase-1ic. No code changes or reopening required.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.4.md) | [sase-1nf.4](sase-1nf.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`682e52f`](https://github.com/sase-org/sase/commit/682e52fc716fd93a1481abbad57a9f219c6877a1) | fix(cleanup): losslessly encode EpicFollowView wait\_epic\_follows in bundles | [sase-1nf.4](sase-1nf.4.md) | 2026-10-20 14:06:08 EDT |

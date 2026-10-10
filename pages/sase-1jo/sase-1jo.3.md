# Bead: sase-1jo.3 — SASE agent-eval pilot harness

[Bead Pages](../README.md) / [sase-1jo](README.md) / sase-1jo.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.6k](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.6k.md) · **Assignee:** `sase-1jo.3` · **Size:** large
**Created:** 2026-10-10 15:45:43 EDT · **Closed:** 2026-10-10 15:53:07 EDT
**Plan:** [202610/databricks\_followups.md](https://github.com/sase-org/sase--plans/blob/main/202610/databricks_followups.md)

## Description

evalpilot: plan and build the small task-success eval over real SASE runs described in the report, kept separate from fakey conformance, with real runs gated by the eval_pilot decision.

## Notes

[2026-10-10T19:52:54Z · sase-1jo.3] Final reviewer decision: eval_pilot = skip. No pilot harness or real runs were produced. Phase sase-1jo.4 must carry this full deferred pilot spec: optional pilot between applying and the onsite, without delaying applications; 8-12 coding tasks from real, already-merged history, each frozen at the selected commit’s parent with that commit’s own tests as oracle in a declarative task manifest; explicit checks for passing tests, scope compliance, and required artifacts, keeping timeouts and failed runs in the denominator; record harness, model, version, and exact prompt for each run; repeat a subset and report variance, pass@k, and per-task outcomes; log runs as MLflow traces and use mlflow.genai.evaluate scorers only when clarifying results, localizing and reporting one regression from a trace; keep fakey conformance results separate from real-agent task-success scores. For any future approved implementation, put dev tooling in tools/agent_eval_pilot/ after reading tools/AGENTS.md; keep MLflow optional (e.g. uv run --with mlflow) with no runtime dependency; consider sase tool run for success-check records and triage evidence; unit tests use a stub launcher and plumbing smoke uses explicitly labeled fakey; real launches from an agent require /sase_run LaunchApproval and waiting uses /sase_monitor. The future README must give one real-pilot command and explain the outcome table and pass@k. These are deferred requirements, not completed capabilities or measured results. Authoritative references: plan:202610/databricks_followups.md and research:202610/databricks_nyc_cv_and_role_pitches/databricks_nyc_cv_and_role_pitches.md (Application plan and timeline, item 4).

[2026-10-10T19:53:07Z · sase-1jo.3] Verified final eval_pilot=skip branch; full deferred pilot spec recorded for sase-1jo.4; no implementation changes or model runs; no remaining phase epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1jo.4](sase-1jo.4.md) ◐ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1jo.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1jo.3.md) | [sase-1jo.3](sase-1jo.3.md) | 0 |

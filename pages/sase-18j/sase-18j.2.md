# Bead: sase-18j.2 — Durable failure items, extractors, and normalization in sase-core

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.2` · **Size:** large
**Created:** 2026-09-24 19:07:03 EDT · **Closed:** 2026-09-24 20:21:59 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

## Description

core-failure-items: add the additive triage tables, the versioned extractor registry and normalization, golden fixtures from real athena logs, early fingerprint_before persistence, retention (including stage output files), and the extract/record/show bindings, in sase-core only.

## Notes

[2026-09-25T00:21:19Z · sase-18j.2] sase phase bindings-and-backtest must move sase-core-revision.txt to a pushed sase-core commit containing this phase's commit (host finalizer creates it) before calling tool_run_triage_extract, tool_run_triage_record, tool_run_triage_show, or sending observe fingerprint_before

[2026-09-25T00:21:32Z · sase-18j.2] Wire summary for sase-18j.3: label JSON fields (knobs, evidence, possible_owners) are opaque in this phase; output_truncated must never yield a continue/no_new_failures; stage key * constant is TOOL_RUN_TRIAGE_STAGE_KEY_RUN_OUTPUT

[2026-09-25T00:21:42Z · sase-18j.2] PROPOSED FOLLOW-UP: specific extractors for lint (pyscripts), lint (feature flags), lint (test waits), and SASE validation (all generic -> UNKNOWN in v1, 33 of 442 failing stage sections on athena)

[2026-09-25T00:21:59Z · sase-18j.2] Implemented core-failure-items in sase-core only; sase repo untouched (git status clean). Verified: sase tool run check succeeded (42e6e653fe6b630091bc294094142c68, ~5min); 82 tool_run + 4 telemetry tests pass incl. 15 golden extractor cases, record/show round-trip, idempotent replay, label first-wins, refusals, fingerprint_before observe/finish keep-first, retention detail/summary cuts with stage_output candidates, cascade compat. sase bead epic-symbols clean.

## Dependencies

- **Blocks:** [sase-18j.3](sase-18j.3.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18j.2.md) | [sase-18j.2](sase-18j.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8315364`](https://github.com/sase-org/sase-core/commit/83153645fe14cdcc34c73b665a93b2cc84e987ee) | feat(triage): durable failure items, extractors, normalization, and extract/record/show bindings | [sase-18j.2](sase-18j.2.md) | 2026-09-24 20:24:05 EDT |

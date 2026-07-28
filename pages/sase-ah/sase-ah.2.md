# Bead: sase-ah.2 — Retire publication requests that can never be published

[Bead Pages](../README.md) / [sase-ah](README.md) / sase-ah.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ah.2` · **Size:** medium
**Created:** 2026-07-28 18:19:17 UTC · **Closed:** 2026-07-28 18:45:38 UTC
**Plan:** [202607/agent\_publication\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_publication_reliability.md)

## Description

terminal-disposition: add a durable terminal disposition to the publication outbox, classify "hood has no publishable runs" as terminal once a retry has confirmed it, and stop `--retry-quarantined` from resurrecting terminal requests into an endless quarantine cycle.

## Notes

[2026-07-28T18:45:29Z · sase-ah.2] Implemented publication-outbox schema v3 with durable terminal/terminal_reason state and schema-1/2 compatibility; confirmed terminal failures retire only after the same prior error, terminal requests are excluded from active work and quarantine retries, and drop_terminal_agent_publications returns/removes retired entries. Wired no-publishable-runs and full-sync materialization failures into terminal classification. Verification: 36 focused tests passed; full suite 23136 passed, 7 skipped; formatting, Ruff, mypy, script lint, toobig, and committed-plan validation passed. Required just check was run but its Symvision and SASE-validation stages are blocked by unrelated checkout/plan-sidecar issues: cross-file private _PlanProvenanceSection imports and missing prompt reverse links on agent_publication_reliability.md and bead_pages.md.

## Dependencies

- **Blocks:** [sase-ah.3](sase-ah.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ah.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ah.2/README.md) | [sase-ah.2](sase-ah.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d8afeb7`](https://github.com/sase-org/sase/commit/d8afeb7b0c0331c24d9bdcf7a4c78679020c9548) | fix(agents-sync): retire terminal publication requests (sase-ah.2) | [sase-ah.2](sase-ah.2.md) | 2026-07-28 18:47:14 |

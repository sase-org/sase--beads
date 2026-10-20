# Bead: sase-1n6.5.1.5.1 — Repair qualification producer and consumer integration

[Bead Pages](../README.md) / [sase-1n6.5.1.5](sase-1n6.5.1.5.md) / sase-1n6.5.1.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1n6.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n6.5.1.land.md) · **Assignee:** `sase-1n6.5.1.5.1` · **Size:** medium
**Created:** 2026-10-20 00:28:15 EDT · **Closed:** 2026-10-20 00:52:16 EDT
**Plan:** [202610/qualification\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/qualification_landing_repairs.md)

## Description

repair: fix authoritative job identity, paginated artifact transport, observation persistence, and refusal diagnostics with executable integration tests.

## Notes

[2026-10-20T04:52:09Z · sase-1n6.5.1.5.1] Repair complete: caller-scoped job identity (ci.yml caller-job input threaded to write_qualification_evidence --caller-job, GITHUB_TOKEN on both evidence steps, git rev-parse HEAD checkout SHA, preflight wheel version recorded before scan and carried when .venv is missing), run-scoped artifacts + --slurp via new collect_qualification_jobs fetch-evidence (concatenated streams decode, duplicate live artifacts refuse, conflicting payload bytes refuse), canonical candidate-gen{generation}-qualification-run{RUN}-attempt{N}.json draft asset written by --out and uploaded by basename with identical-no-op/conflict-refuse, command diagnostics preserved beside binding mismatch, fetch-error red keeps expected run/attempt and revalidates typed QUALIFY_RED rerun_eligible=false through qualify CLI and evaluate (steward adapter), rerun docs narrowed to first-attempt all-tests failures. Contracts for deployed-proof: observation asset candidate-gen{generation}-qualification-run{RUN}-attempt{N}.json; rehearse artifact qualification-observation-run-{run}-attempt-{attempt}; fetch-evidence --repo R --run-id R --attempts N --jobs-dir J --artifacts-file run.json --evidence-root E --zips-dir Z; verification: sase tool run check 4460fc1842cf377b80188593d42803ab succeeded (all lint gates + scoped lane, 177 focused tests green incl. new tests/test_qualification_transport_integration.py).

[2026-10-20T04:52:16Z · sase-1n6.5.1.5.1] All six repair items implemented with executable integration tests: scoped job identity, run-scoped artifact transport, canonical draft asset, preflight version + diagnostics, fetch-error red identity, rerun docs. sase tool run check 4460fc18 succeeded; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1n6.5.1.5.2](sase-1n6.5.1.5.2.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n6.5.1.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.1/README.md) | [sase-1n6.5.1.5.1](sase-1n6.5.1.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`400572e`](https://github.com/sase-org/sase/commit/400572eab602681aa64f44653484a1dfc9ab0b38) | fix(release): repair qualification evidence transport and prove it | [sase-1n6.5.1.5.1](sase-1n6.5.1.5.1.md) | 2026-10-20 00:53:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n6.5.1.5.1][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n6.5.1.5.1/README.md

<!-- sase:referenced-by:end -->

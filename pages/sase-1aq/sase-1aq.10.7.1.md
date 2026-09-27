# Bead: sase-1aq.10.7.1 — Repair exact remote operations on fleet-dispatched agents

[Bead Pages](../README.md) / [sase-1aq.10.7](sase-1aq.10.7.md) / sase-1aq.10.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.land.md) · **Assignee:** `sase-1aq.10.7.1` · **Size:** medium
**Created:** 2026-09-26 20:01:52 EDT · **Closed:** 2026-09-26 20:57:21 EDT
**Plan:** [202609/1aq\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_remaining_acceptance.md)

## Description

exact_ops: make settled dispatch rows addressable and prove exact stop and retry on a released cohort.

## Notes

[2026-09-27T00:36:40Z · sase-1aq.10.7.1] PROPOSED FOLLOW-UP: killed fleet-dispatched rows are reaped (dispatch-2371a0f6e94cd270eda646012b3a23d4 artifacts lost done.json, index row deleted within ~30min of remote stop) so retry-after-kill cannot address them — owner to decide whether reaping or retry-context retention is intended

[2026-09-27T00:36:54Z · sase-1aq.10.7.1] PROPOSED FOLLOW-UP: remote stop/retry receipts go uncertain on the 5s request timeout (3/3 stops, 1/4 retries this phase) while Apollo applies the effect — consider a longer mutation acceptance window or async receipt polling before replay

[2026-09-27T00:37:07Z · sase-1aq.10.7.1] PROPOSED FOLLOW-UP: fresh dispatch rows stay invisible to catalog_sync for ~7min (snapshot rebuild lag) — exact stop attempted inside that window still reports no remote agent matching; consider documenting the window or serving provisional launch rows

[2026-09-27T00:57:21Z · sase-1aq.10.7.1] exact_ops done 2026-09-27T00:55Z: root cause traced (lookup omitted include_terminal; agent_id exact-match missed receipt-key vs landed --N turn ids; settled project sase vs landed project home); fixed machine.py + tests; core/binding regressions green, no pin move; live proof dispatch-39f835d38a0891b084e61be84de58bab exact stop killed Apollo pid + retry x3 under one settled key -> single .r0; gateway bare-sase bridge verified; evidence on .7.6/sase-1aq.5; 3 PROPOSED FOLLOW-UPs recorded; epic-symbols clean; scoped gates green (ruff/fmt/mypy/focused pytest/cargo), full just check unfinished (cold Rust rebuild exceeds turn limits, no new red)

## Dependencies

- **Blocks:** [sase-1aq.10.7.2](sase-1aq.10.7.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.1/README.md) | [sase-1aq.10.7.1](sase-1aq.10.7.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb0b91e`](https://github.com/sase-org/sase/commit/fb0b91edce9b75f1c84002016aa27c83b7a9fafb) | fix(machine): repair exact remote stop/retry lookup for fleet-dispatched agents | [sase-1aq.10.7.1](sase-1aq.10.7.1.md) | 2026-09-26 21:00:24 EDT |
| sase-core | [`sase-core@b2e4ea6`](https://github.com/sase-org/sase-core/commit/b2e4ea6672c47dbf101ad77c0ff8bd9352e4b124) | test(fleet): add catalog and binding terminal-flag coverage | [sase-1aq.10.7.1](sase-1aq.10.7.1.md) | 2026-09-26 21:03:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1aq.10.7.1][1] | Need full phase history and notes for exact_ops work | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.1/README.md

<!-- sase:referenced-by:end -->

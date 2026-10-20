# Bead: sase-1n8.3 — sase: show the host-completion recovery reason to the follow-up agent

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.3` · **Size:** small
**Created:** 2026-10-20 06:53:00 EDT · **Closed:** 2026-10-20 07:45:28 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Description

recovery-reason-prompt: persist every recovery reason and render a Host completion section with glosses in monitor follow-up prompts.

## Notes

[2026-10-20T11:45:14Z · sase-1n8.3] PROPOSED FOLLOW-UP: just check has 3 pre-existing failures that reproduce identically on the clean base tree (verified via git stash) — test_app_import_budget (3523 modules vs 3522 cap, +0 from this phase), test_contract_manifest_matches_marker_selection (stale manifest ordering), and test_models_panel_provider_modal_priority (passes in isolation; full-suite ordering flake)

[2026-10-20T11:45:28Z · sase-1n8.3] Implemented recovery-reason prompt: recover_host_completion persists full reasons list in host_completion_receipt.json and monitor_host_completion_reasons meta; follow-up prompts render a Host completion section with per-reason glosses before Your next action; docs updated. Verified: 4 new regression tests pass, all followup-prompt + host-completion suites pass (56 tests), sase tool run check lint/validation/docs gates all green; 3 remaining failures (import budget, contract manifest, models panel) reproduce identically on clean base tree and are recorded as PROPOSED FOLLOW-UP.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1n8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.3/README.md) | [sase-1n8.3](sase-1n8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e77280c`](https://github.com/sase-org/sase/commit/e77280c873763035f3e03cd4256f06af95d52f80) | feat(monitor): show host-completion recovery reasons in follow-up prompts | [sase-1n8.3](sase-1n8.3.md) | 2026-10-20 07:46:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n8.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.3/README.md

<!-- sase:referenced-by:end -->

# Bead: sase-1oh.5.1.2 — Withhold unsafe run files without breaking snapshots or clean runs

[Bead Pages](../README.md) / [sase-1oh.5.1](sase-1oh.5.1.md) / sase-1oh.5.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.5.md) · **Assignee:** `sase-1oh.5.1.2` · **Size:** medium
**Created:** 2026-10-26 14:45:04 EDT · **Closed:** 2026-10-26 20:15:31 EDT
**Plan:** [202610/agents\_publication\_secret\_scan.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_publication_secret_scan.md)

## Description

transcript-publication: enforce the protection contract in full and targeted hood publication, including richer-file fallback, rendering, manifests, and staging; prove clean runs still publish.

## Notes

[2026-10-27T00:15:06Z · sase-1oh.5.1.2] PROPOSED FOLLOW-UP: 3 scoped-lane failures reproduce identically on the clean base tree (verified via git stash): test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_blocked_head_then_high_budget_launch_uses_real_scan (both tests/test_run_agent_runner_slot_scan_capacity.py), test_capacity_only_skips_done_dirs_and_keeps_active_ones (tests/test_core_agent_scan_options.py). No task bead tracks them. Full check: 57723 passed, 17 skipped; only these 3 fail.

[2026-10-27T00:15:12Z · sase-1oh.5.1.2] PROPOSED FOLLOW-UP: completion/accounting for withheld transcript runs is still generic: a structurally-withheld run fails publication_request_fulfilled and retires with did-not-materialize wording instead of a blocked-aware settlement, and per-request unverified-withheld runs are charged rather than parked. Needs structured blocked/unverified outcome propagation through direct publish and completion/accounting (see prompt-publication and rejection-recovery phases) before the lander finishes.

[2026-10-27T00:15:31Z · sase-1oh.5.1.2] Transcript protection enforced: snapshot gating withholds unsafe prompt/chat/workflow/prompt-step files (whole run when meta/state/commits hit), richer-file merge consults ledger plus rescan, planning threads scope and surfaces withheld diagnostics, pre-stage verification scans only HEAD-differing blobs and fails closed on digest change. Verified: 8 new tests pass; existing publication/git-sync/commit suites pass (61+42); sase tool run check 57723 passed with only 3 failures that reproduce identically on the clean base (recorded as follow-ups). Justfile gained 2 epic-symbol rows keyed to sase-1oh.5.1; none remain for this phase. Note: linked sase-core checkout left detached at d14a32c8 (pin 416db289 plus one unrelated commit) to match the installed extension and stop refresh churn; refresh tooling leaves detached checkouts alone.

## Dependencies

- **Depends on:** [sase-1oh.5.1.1](sase-1oh.5.1.1.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oh.5.1.3](sase-1oh.5.1.3.md) ◐ · ⧖ 2026-10-26
- **Blocks:** [sase-1oh.5.1.4](sase-1oh.5.1.4.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oh.5.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.5.1.2/README.md) | [sase-1oh.5.1.2](sase-1oh.5.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`67edb96`](https://github.com/sase-org/sase/commit/67edb9677d23a2cdc93b71d944c551336f6416e3) | feat(agents-sync): withhold unsafe transcript bytes without breaking clean publication | [sase-1oh.5.1.2](sase-1oh.5.1.2.md) | 2026-10-26 20:17:10 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oh.5.1.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1oh.5.1.2/README.md

<!-- sase:referenced-by:end -->

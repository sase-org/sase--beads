# Bead: sase-1aq.10.7.5 — Close the original sase-1aq live gates in place

[Bead Pages](../README.md) / [sase-1aq.10.7](sase-1aq.10.7.md) / sase-1aq.10.7.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.land.md) · **Assignee:** `sase-1aq.10.7.5.land`
**Created:** 2026-09-26 21:57:07 EDT
**Plan:** [202609/1aq\_close\_original\_gates.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_close_original_gates.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/1aq_close_original_gates.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/1aq_close_original_gates.md

<!-- sase:links:end -->

## Description

The original remote-dispatch, owner-to-viewer parity, and dispatch-memory beads pass their own acceptance criteria and close normally. Work is not handed to owners that are not running.

## Notes

[2026-09-27T06:19:46Z · sase-1aq.10.7.5.land] LAND AUDIT (sase-1aq.10.7.5.land, 2026-09-27), interrupted for remaining work. Verified: all 6 phases closed, and every phase note was reviewed. Epic commits: sase 700b37b384 (exact_ops_receipts client) and 19abe261d4 (dispatch memory); sase-core 37a4dd8 (fencing proof) and b57cd21 (gateway settled receipts, fresh-launch overlay, killed-row retention). b57cd21 changes no Python binding, and the fleet_validate_mutation_request surface already exists at pin e44af7d, so no pin move is needed. There are no epic-symbol entries. Integration: the post-start commits 86fac2f103, 0ed46f5fdb, 55e9e96dec and f83a648ebb do not touch dispatch, mutation, mobile-kill or remote-dispatch docs code, so nothing needed integrating.

Remaining epic work found, planned as a child epic with parent_bead sase-1aq.10.7.5:
(1) The exact_ops_receipts contract was never deployed or proven live. Neither host's sase contains 700b37b384 (or fb0b91edce): Apollo is at 64fae010f.dirty and Athena at 63d2bdcea.dirty. Neither host's sase-core contains b57cd21 (both at e44af7d), and the Apollo gateway started before b57cd21 existed. live_matrix reused pre-epic evidence and credited "no-reap retention" to the undeployed .5.2 contract. sase update -n skips the sase fast-forward on both hosts because the primary checkouts carry dirty hand-applied copies of 29f8240df5 and fb0b91edce.
(2) Two defects from 700b37b384: a mypy arg-type error at dispatch/mutations.py:143, float(request[...]); and a broad except-TypeError fallback in the _mobile_agent_deps.kill_named_agent wrapper, which broke test_kill_mobile_agent_bridge_returns_success_for_stale_cleanup and could re-run a real kill without retain_for_retry. The land agent verified the fix locally (61 focused tests green, mypy clean), but a plan handoff cannot commit, so the child phase receipt_cleanup re-applies it.

just check (ToolRun 109aa65ee68b1d6365d33d297620dfab, after just install rebuilt the stale 0.34.71 workspace binding) shows only clean-base reds. mypy: 4 errors, owned by sase-1ab and sase-19i.7.3.3.3.3 (corroborating notes added). symvision: 13 errors, filed as sase-1ay. test-scoped: 48 failures, all rename fallout; the 5 labeled NEW reproduce on a stash-clean tree.

PROPOSED FOLLOW-UP dispositions:
- .5.1 #1 (mypy): already a DISCOVERED ISSUE on sase-1ab and on sase-19i.7.3.3.3.3; corroborated.
- .5.2 clippy: +1 on sase-1an.
- .5.2 "check times out rebuilding sase-core-rs", .5.2 kill_dismiss wire 9, .5.3 #1 dispatch_launch, .5.3 #3, .5.4 #1, .5.5 #3 (tailnet facade test) and .5.6 #1: declined. All were the stale 0.34.71 workspace binding; after just install these suites pass.
- .5.3 #2 (sase skew), .5.3 #4 (bridge fix absent on Athena) and .5.4 #3 (Athena index gate_shell_id): folded into the child phase matched_deploy.
- .5.4 #2 (fleet golden drift): declined. fix-tui-screenshots --check on followed_partial_offline and keyboard_focus_and_narrow is clean with the rebuilt binding.
- .5.5 #1: new sase-1av (attention next_cursor paging).
- .5.5 #2: new sase-1aw (cache-only reads reported as ok).
- .5.5 #4: new sase-1ax (machines_pane flake).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.land.md) | [sase-1aq.10.7.5](sase-1aq.10.7.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1aq.10.7.5.5][1] | ancestor_landing audit: confirm sibling phase closure | 1 |
| read-by | [agent:sase-1aq.10.7.5.6][2] | phase detail | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.6/README.md

<!-- sase:referenced-by:end -->

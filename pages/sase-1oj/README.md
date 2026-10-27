# Bead: sase-1oj — Cut athena's SSD writes from SASE's own churn

[Bead Pages](../README.md) / sase-1oj

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.land`
**Created:** 2026-10-26 16:07:27 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/athena_disk_write_diet.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md

<!-- sase:links:end -->

## Description

SASE stops rewriting large derived state on athena's root NVMe. The runner-slot capacity cache shrinks from ~104 MB to under ~1 MB. Codex launches stop rebuilding a 347 MB thread index (and start ~3 minutes sooner). The corrupt bead read-model cache heals itself instead of rebuilding and rolling back on every read. sase-core test builds link ~2.9 GB less per cycle. No admission decision, Codex transcript, or bead read result changes.

## Notes

[2026-10-27T02:05:05Z · sase-1ok.land] DISCOVERED ISSUE: Landing triage of sase-1ok.1#1, sase-1ok.2#1, and sase-1ok.3#2 finds the same three capacity fixtures failing after sase-1oj.1 dead-PID pruning: test_capacity_only_skips_done_dirs_and_keeps_active_ones, test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_blocked_head_then_high_budget_launch_uses_real_scan. The phases independently reproduced failures on clean base 98cb07ebb8 / witness 0eefa7f1c9ee0383c9c47942325079fe; fixture PID 11111 is not a liveness guarantee. sase-1oj.4#2 reports correcting these fixtures and passing ToolRun ad01b1a3661b647ee62905f865c53150, but those adoption files are not in fetched origin/master cef4bb1199 at this audit. Please include that reported fix in this epic landing. Causally owned here; no new task bead.

[2026-10-27T02:11:04Z · sase-1ok.land] FOLLOW-UP TO LANDING EVIDENCE: e7d9f7a479 (sase-1oj.4 adoption) landed during the audit and was fast-forwarded locally. Focused verification of tests/test_core_agent_scan_options.py, test_run_agent_runner_slot_poll.py, test_run_agent_runner_slot_scan_capacity.py, and test_capacity_only_scan_parity.py now gives 36 passed, 1 failed. Remaining exact node: test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, tests/test_run_agent_runner_slot_scan_capacity.py:90, drained is unexpected instead of None. This function still supplies fake PIDs 100, 101, 102; e7d9f7a479 changed only the other real-scan test to os.getpid(). That leftover fixture remains part of the dead-PID-pruning adoption. Other two previously proposed failures now pass. Clean tracked tree, no sase-1ok changes authored.

[2026-10-27T03:01:40Z · sase-1ok.land] INDEPENDENT REPRODUCTION: sase-1ok tale coder ToolRun 27aed0c963ecf9fe21d2881b3d2d3fcf (sase tool run check) still fails tests/test_run_agent_runner_slot_scan_capacity.py::test_capacity_blocked_waiter_does_not_park_the_queue_behind_it. Assertion is drained == 'unexpected' instead of None at the claim that must park; the fixture still uses fake PIDs 100/101/102. Same remaining node recorded on this epic after e7d9f7a479. Unrelated to stranded-wait reconciliation. No new task.

[2026-10-27T03:15:28Z · sase-1oh.4.1.land] DISCOVERED ISSUE: Landing triage of sase-1oh.4.1.3 note #1 independently reproduces the remaining dead-PID fixture after e7d9f7a479 on sase c74a32c5c4. Focused run of test_agent_group_revival_e2e.py, test_axe_chop_bead_claim_checks.py, test_axe_chop_bead_claim_checks_leases.py, test_run_agent_runner_slot_scan_capacity.py, and test_core_agent_scan_options.py: 47 passed, only test_capacity_blocked_waiter_does_not_park_the_queue_behind_it failed at line 90 (drained unexpected, expected None). Fixture still uses PIDs 100/101/102. Other proposed capacity nodes now pass. This corroborates this epic notes #2/#3 and belongs to dead-PID pruning adoption, not failed-close recovery. No new task.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1oj.1](sase-1oj.1.md) | Prune never-live dirs from the capacity\_only scan | ✓ closed | medium | 2026-10-26 | 1 | 1 |
| [sase-1oj.2](sase-1oj.2.md) | Self-heal the corrupt bead read-model cache | ✓ closed | medium | 2026-10-26 | 1 | 1 |
| [sase-1oj.3](sase-1oj.3.md) | Consolidate sase-core integration-test binaries | ✓ closed | medium | 2026-10-26 | 1 | 2 |
| [sase-1oj.4](sase-1oj.4.md) | Adopt the pruned capacity scan in sase | ✓ closed | small | 2026-10-26 | 1 | 2 |
| [sase-1oj.5](sase-1oj.5.md) | Stop per-launch Codex thread backfill | ✓ closed | medium | 2026-10-26 | 1 | 1 |
| [sase-1oj.6](sase-1oj.6.md) | Measure the write reduction on athena | ◐ in_progress | small | 2026-10-26 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1oj: Cut athena's SSD writes from SASE's own churn [in_progress]"]
    n1["sase-1oj.1: Prune never-live dirs from the capacity_only scan [closed]"]
    n2["sase-1oj.2: Self-heal the corrupt bead read-model cache [closed]"]
    n3["sase-1oj.3: Consolidate sase-core integration-test binaries [closed]"]
    n4["sase-1oj.4: Adopt the pruned capacity scan in sase [closed]"]
    n5["sase-1oj.5: Stop per-launch Codex thread backfill [closed]"]
    n6["sase-1oj.6: Measure the write reduction on athena [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n3
    n1 -.-> n4
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.1/README.md) | [sase-1oj.1](sase-1oj.1.md) | 1 |
| [bbugyi200.apollo.sase-1oj.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.2/README.md) | [sase-1oj.2](sase-1oj.2.md) | 1 |
| [bbugyi200.apollo.sase-1oj.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.3/README.md) | [sase-1oj.3](sase-1oj.3.md) | 2 |
| [bbugyi200.apollo.sase-1oj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.4.md) | [sase-1oj.4](sase-1oj.4.md) | 2 |
| [bbugyi200.apollo.sase-1oj.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.5.md) | [sase-1oj.5](sase-1oj.5.md) | 1 |
| [bbugyi200.apollo.sase-1oj.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.6/README.md) | [sase-1oj.6](sase-1oj.6.md) | 0 |
| [bbugyi200.apollo.sase-1oj.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.land/README.md) | [sase-1oj](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@d14a32c`](https://github.com/sase-org/sase-core/commit/d14a32c8242aea936f39711a8452ef0ba08b121d) | feat(agent-scan): prune never-live capacity records | [sase-1oj.1](sase-1oj.1.md) | 2026-10-26 17:21:29 EDT |
| sase-core | [`sase-core@651d193`](https://github.com/sase-org/sase-core/commit/651d19330651f911ffdf20c8768d7b3a3d5e2634) | fix(bead-read-model): repair corrupt caches in place | [sase-1oj.2](sase-1oj.2.md) | 2026-10-26 18:05:21 EDT |
| sase-core | [`sase-core@b12e581`](https://github.com/sase-org/sase-core/commit/b12e5815289b1a83c244ab2bc7d620fa3eb662be) | test(core): merge integration tests into one binary per crate | [sase-1oj.3](sase-1oj.3.md) | 2026-10-26 18:52:13 EDT |
| sase | [`60498dc`](https://github.com/sase-org/sase/commit/60498dcb5ec08bd945a8e89055c74e182065fbab) | docs(rust-backend): point test paths at consolidated integration targets | [sase-1oj.3](sase-1oj.3.md) | 2026-10-26 18:56:43 EDT |
| sase | [`d6d8b2b`](https://github.com/sase-org/sase/commit/d6d8b2b9425ae2c4e88aa689ad8a89c03852732b) | feat(codex): isolate shadow-home sessions to today and tomorrow | [sase-1oj.5](sase-1oj.5.md) | 2026-10-26 19:48:02 EDT |
| sase | [`e7d9f7a`](https://github.com/sase-org/sase/commit/e7d9f7a479664f412422ce40c0e679d29e5db41c) | feat(runner-slots): adopt pruned capacity scan | [sase-1oj.4](sase-1oj.4.md) | 2026-10-26 22:05:57 EDT |
| sase | [`f837112`](https://github.com/sase-org/sase/commit/f83711219c0c5cb137d5b94a25a8923cd7357adf) | test(runner-slots): pin live pids in capacity-scan adoption tests | [sase-1oj.4](sase-1oj.4.md) | 2026-10-26 23:45:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oj.2][1] | Need epic plan, phase notes, constraints and design details for assigned phase | 1 |
| read-by | [agent:sase-1oj.4][2] | Need parent epic status and remaining phases | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.4.md

<!-- sase:referenced-by:end -->

# Bead: sase-1ex.11 — Make \`\<space\>\` reveal a pre-built hidden prompt bar

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.11` · **Size:** large
**Created:** 2026-10-02 14:53:58 EDT · **Closed:** 2026-10-03 11:14:25 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

space-hot-spare: after re-measuring, keep one fresh, inert, hidden, id-less prompt bar mounted at idle. `<space>` seeds it, reveals it, and calls a new `activate()`. Other prompt modes keep fresh mounts, and every session still gets a new instance.

## Notes

[2026-10-03T13:35:15Z · sase-1ex.11] space-hot-spare bench before (no spare): first_space p50/p95/max 82.64/82.64/82.64 ms, steady_space p50/p95/max 127.55/450.18/450.18 ms. Gate fails as expected (both p95 > 60 ms), proceeding with spare.

[2026-10-03T13:35:26Z · sase-1ex.11] space-hot-spare bench after (hidden spare landed): first_space p50/p95/max 236.41/236.41/236.41 ms, steady_space p50/p95/max 139.16/172.42/172.42 ms. p95 stays above 60 ms. PROPOSED FOLLOW-UP: overlay-dock the prompt bar — reveal still misses 60 ms after the hidden spare.

[2026-10-03T15:08:19Z · sase-1ex.11--2] Verification status (monitor yc8qn0z1nqzh follow-up): hot-spare implementation complete per plan; 8/8 tests in tests/ace/tui/test_prompt_bar_hot_spare.py pass. just check still red: test_dev_extension_exposes_every_collected_name fails deterministically on clean base too (src/sase/core/publication_payload_facade.py requires sase_core_rs.plan_publication_payload_batches, which the linked sase-core checkout does not expose; only plan_agent_publication_batches exists) — pre-existing, not caused by this phase. Remaining full-suite failures (launch_context rebroadcast, prompt_tab focus, demand_runs peak RSS, agents multi-agent PNG golden) all pass in isolation on this tree and reproduce on base under load; treated as flakes/pre-existing drift. PROPOSED FOLLOW-UP: reconcile publication_payload_facade binding (rename to plan_agent_publication_batches or land the Rust binding) and refresh the agents multi-agent PNG golden.

[2026-10-03T15:14:25Z · sase-1ex.11--2] Closed by explicit `sase stitch create -B close` after create_commit landed 90193a05d5 ("feat(prompt-bar): implement space hot spare phase with lifecycle wiring"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-1ex.11` if more work remains.

## Dependencies

- **Depends on:** [sase-1ex.10](sase-1ex.10.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.12](sase-1ex.12.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.3](sase-1ex.3.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.4](sase-1ex.4.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.5](sase-1ex.5.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.6](sase-1ex.6.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.7](sase-1ex.7.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.8](sase-1ex.8.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.9](sase-1ex.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.11.md) | [sase-1ex.11](sase-1ex.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`90193a0`](https://github.com/sase-org/sase/commit/90193a05d51a7e1339ad9567a8533a870b951c99) | feat(prompt-bar): implement space hot spare phase with lifecycle wiring | [sase-1ex.11](sase-1ex.11.md) | 2026-10-03 11:10:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.11--2][1] | implement approved space_hot_spare plan and repair check failures | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ex.11.md

<!-- sase:referenced-by:end -->

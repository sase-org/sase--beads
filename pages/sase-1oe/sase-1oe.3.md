# Bead: sase-1oe.3 — Master pins the published core that contains its source revision

[Bead Pages](../README.md) / [sase-1oe](README.md) / sase-1oe.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14h.md) · **Assignee:** `sase-1oe.3` · **Size:** small
**Created:** 2026-10-26 08:35:13 EDT · **Closed:** 2026-10-26 18:37:45 EDT
**Plan:** [202610/unblock\_e2\_release\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_release_cutover.md)

## Description

core-pin: once a complete published sase-core-rs (expected 0.42.7) contains sase-core-revision.txt, ratchet master's exact pin and uv.lock to it. If that tag also carries the cut-red fix, move the revision pin to the tag commit so the steward builds the fixed policy.

## Notes

[2026-10-26T14:04:00Z · sase-1oe.3] core-pin waiting on daily core cut: sase-core-revision.txt=f95690648dadfbe9a1f02e3282f1840f81ed6589 which is the cut-red fix commit itself (parent 67b77d0561fb); ratchet_core_pin --check exits 3 CORE_LAG newest_complete=0.42.6; decision core_cut=wait so handing 36h poll to monitor

[2026-10-26T22:36:24Z · sase-1oe.3--3] PROPOSED FOLLOW-UP: dev-workspace just check builds sase_core_rs from linked sase-core master and goes red on 3 capacity-scan tests (test_capacity_only_skips_done_dirs_and_keeps_active_ones, test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_blocked_head_then_high_budget_launch_uses_real_scan) because unreleased sase-core d14a32c8 (feat agent-scan: prune never-live capacity records, in linked master 651d1933 but absent from published v0.42.7) changes scan behavior the sase tests do not encode. Reproduced: master-built wheel (manylinux_2_39 local build) fails all 3; published 0.42.6 and published 0.42.7 (SHA256 f1c64968) pass all 3. Owner: whoever owns agent-scan integration (sase-side test update or core-cut coordination), not core-pin.

[2026-10-26T22:37:45Z · sase-1oe.3--3] core-pin complete: pinned to published sase-core-rs 0.42.7 (sase-core-revision.txt=4121de03ba0aac45cc8b6c55a5113207f0e42535, v0.42.7 tag commit containing cut-red fix f95690648dadfbe9a1f02e3282f1840f81ed6589 and 67b77d05). Verified: ratchet_core_pin --check exits PINNED(0.42.7); check_sase_core_rs_bindings 880/880 on the published wheel (SHA256 f1c64968 verified against PyPI); 55 release-steward/release tests green on published 0.42.7; the 3 capacity-scan tests that failed in tool run 98bebed7687074511ffc5349e99a72f7 pass on published 0.42.6 and published 0.42.7 and fail only with the dev-workspace master-built wheel (unreleased d14a32c8) — filed as PROPOSED FOLLOW-UP for the agent-scan lane; all lint/fmt stages green on this tree; epic-symbols clean. Diff touches only pyproject.toml, uv.lock, sase-core-revision.txt.

## Dependencies

- **Depends on:** [sase-1oe.2](sase-1oe.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oe.4](sase-1oe.4.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1oe.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oe.3.md) | [sase-1oe.3](sase-1oe.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`816efdc`](https://github.com/sase-org/sase/commit/816efdc9d755fc26e8f832956b0ec8936c180213) | chore(core): ratchet sase-core-rs pin to published 0.42.7 | [sase-1oe.3](sase-1oe.3.md) | 2026-10-26 20:31:39 EDT |

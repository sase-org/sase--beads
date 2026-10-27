# Bead: sase-1oj.4 — Adopt the pruned capacity scan in sase

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.4` · **Size:** small
**Created:** 2026-10-26 16:07:28 EDT · **Closed:** 2026-10-26 23:43:53 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

## Previously Closed

> ↺ Closed 2026-10-27T02:14:52Z · done
>
> (none)
>
> Reopened 2026-10-27T03:19:14Z by `sase bead open`

> ↺ Closed 2026-10-27T01:00:11Z · done
>
> (none)
>
> Reopened 2026-10-27T02:12:36Z by `sase bead open`

## Description

sase-capacity-adopt: ratchet sase-core-revision.txt past both core phases, add a Python differential admission test through the real binding, sweep stale scan-cache temp files, and update the capacity_only docstring and runner-slot docs.

## Notes

[2026-10-27T00:59:52Z · sase-1oj.4] PROPOSED FOLLOW-UP: Triage the remaining unrelated failures from `sase tool run check` ToolRun 5721d601c1ba2453537c837556798089 (25 tests remained after the three capacity-specific failures were corrected and passed in ToolRun ad01b1a3661b647ee62905f865c53150). Existing related reports include sase-1ew, sase-1al, sase-1l3, sase-1ia, sase-1hy, sase-1ki, sase-1o5.2, sase-1nn.8.1, and sase-1np; the remaining sudo settlement timeout has no matching bead found.

[2026-10-27T01:00:11Z · sase-1oj.4] Implemented the sase adoption: pinned sase-core at 651d1933 (after both required core phases), documented capacity-only pruning, added the real-binding differential admission regression, swept stale scan temp files older than one hour, and updated runner-slot docs. The three capacity-specific tests pass in ToolRun ad01b1a3661b647ee62905f865c53150; git diff --check passes and epic-symbols reports none. Full ToolRun 5721d601c1ba2453537c837556798089 reached 57,677 passed but failed 28 unrelated tests; recorded follow-up for the 25 remaining cases.

[2026-10-27T02:14:52Z · sase-1oj.4] Finished leftover adoption gaps: real-scan waiter/metadata fixtures now use os.getpid() instead of host-dependent fake PIDs, and the capacity-only parity test asserts a standalone stopped dir is pruned. Pin 03dce1f2 is already past both core phases. Targeted tests: 7 passed (parity, scan-capacity, golden capacity_only, stale-temp prune). epic-symbols none.

[2026-10-27T03:22:34Z · sase-1oj.4--1] Leftover dead-pid fixture gaps: waiter tests now use os.getpid(); parity test prunes a standalone stopped dir and compares admission claims/waiters/weights. Targeted pytest 6 passed. epic-symbols none. Closing after just check.

[2026-10-27T03:43:53Z · sase-1oj.4--2] Restored in_progress after host close_ineligible_status (bead was OPEN after reopen). Leftover real-scan fixtures use os.getpid(); capacity-only parity prunes a standalone stopped dir and compares admission claims/waiters/occupied weights. Pin 03dce1f2 is past both core phases. Targeted pytest 5 passed; prior just check monitor aa2yw47f48r9 exit 0. epic-symbols none.

## Dependencies

- **Depends on:** [sase-1oj.1](sase-1oj.1.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oj.2](sase-1oj.2.md) ✓ · ⧖ 2026-10-26
- **Blocks:** [sase-1oj.6](sase-1oj.6.md) ◐ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.4.md) | [sase-1oj.4](sase-1oj.4.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7d9f7a`](https://github.com/sase-org/sase/commit/e7d9f7a479664f412422ce40c0e679d29e5db41c) | feat(runner-slots): adopt pruned capacity scan | [sase-1oj.4](sase-1oj.4.md) | 2026-10-26 22:05:57 EDT |
| sase | [`f837112`](https://github.com/sase-org/sase/commit/f83711219c0c5cb137d5b94a25a8923cd7357adf) | test(runner-slots): pin live pids in capacity-scan adoption tests | [sase-1oj.4](sase-1oj.4.md) | 2026-10-26 23:45:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1oj.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1oj.4.md

<!-- sase:referenced-by:end -->

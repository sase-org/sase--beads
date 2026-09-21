# Bead: sase-14n.3 — Settle the land segment's queue weight

[Bead Pages](../README.md) / [sase-14n](README.md) / sase-14n.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oe.md) · **Assignee:** `sase-14n.3` · **Size:** medium
**Created:** 2026-09-20 17:14:10 EDT · **Closed:** 2026-09-20 17:53:26 EDT
**Plan:** [202609/fix\_triaged\_bug\_and\_ci\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_triaged_bug_and_ci_beads.md)

## Description

queue_weight: decide from the documented weighted-capacity contract whether the rendered land segment must claim weight 2.0, then fix the renderer or the test accordingly.

## Notes

[2026-09-20T21:52:40Z · sase-14n.3--1] PROPOSED FOLLOW-UP: just check symvision lint red is pre-existing sase-13s - 26 unused public symbols in sdd clone, runner-slot capacity, service host splits reproduced on this tree; matches READY task sase-13s, unrelated to queue-weight test edit, left for land agent triage

[2026-09-20T21:53:26Z · sase-14n.3--1] Settled land-segment queue-weight on test side: land/phase queue_weight None non-explicit, heavy fixture 4.0, renamed omitted-capacity test with full-budget park case. Verified tests/test_capacity_gate_to_admission.py 2 passed plus neighbors test_bead_xprompt_tags 19 passed and capacity suites 27 passed; just check otherwise green except pre-existing symvision 26-symbol red tracked by READY sase-13s (recorded as PROPOSED FOLLOW-UP). Task sase-13o still READY, left for land agent.

## Dependencies

- **Blocks:** [sase-14n.12](sase-14n.12.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14n.13](sase-14n.13.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14n.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-14n.3.md) | [sase-14n.3](sase-14n.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`19c515e`](https://github.com/sase-org/sase/commit/19c515e0ae7efe6642441f8a460cb892c3216537) | test(capacity): settle land-segment queue weight to default contract | [sase-14n.3](sase-14n.3.md) | 2026-09-20 17:55:04 EDT |

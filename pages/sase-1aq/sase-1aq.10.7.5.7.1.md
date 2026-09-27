# Bead: sase-1aq.10.7.5.7.1 — Land the settled-receipt type and kill-wrapper fixes

[Bead Pages](../README.md) / [sase-1aq.10.7.5.7](sase-1aq.10.7.5.7.md) / sase-1aq.10.7.5.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.land.md) · **Assignee:** `sase-1aq.10.7.5.7.1` · **Size:** small
**Created:** 2026-09-27 02:20:33 EDT · **Closed:** 2026-09-27 02:30:47 EDT
**Plan:** [202609/1aq\_receipts\_matched\_live\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md)

## Description

receipt_cleanup: fix the mypy arg-type error in dispatch mutations and the over-broad TypeError fallback in the mobile kill wrapper that exact_ops_receipts introduced, update the stale test fakes, and verify.

## Notes

[2026-09-27T06:30:21Z · sase-1aq.10.7.5.7.1] PROPOSED FOLLOW-UP: sase tool run check stays red on identical clean-base tree (verified via git stash at 19abe261d4): 4 mypy errors (_tree.py:622-629 owned by sase-19i.7.3.3.3.3, _agent_display_hint_sections.py:74 owned by sase-1ab) + 13 symvision unused-public symbols (owned by task sase-1ay); none in files this phase touched

[2026-09-27T06:30:47Z · sase-1aq.10.7.5.7.1] receipt_cleanup done: acceptance_window computed before request and passed as timeout_seconds (float()/mutate_timeout removed); kill_named_agent TypeError fallback removed; 3 test fakes accept retain_for_retry. Verified: 61 focused tests pass (dispatch_mutations, mobile_agent*, kill_named_agent_dismiss), mypy clean on mutations.py, check shows only clean-base reds confirmed identical via stash

## Dependencies

- **Blocks:** [sase-1aq.10.7.5.7.2](sase-1aq.10.7.5.7.2.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.7.1/README.md) | [sase-1aq.10.7.5.7.1](sase-1aq.10.7.5.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`48c3e0d`](https://github.com/sase-org/sase/commit/48c3e0ddc5b822d1eb9985b843c707346322b28d) | refactor(dispatch): receipt cleanup for acceptance window and kill retry | [sase-1aq.10.7.5.7.1](sase-1aq.10.7.5.7.1.md) | 2026-09-27 02:33:46 EDT |

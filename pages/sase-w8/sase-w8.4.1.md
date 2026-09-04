# Bead: sase-w8.4.1 — Consume resolved launch records only after action initiation

[Bead Pages](../README.md) / [sase-w8.4](sase-w8.4.md) / sase-w8.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-w8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w8.land.md) · **Assignee:** `sase-w8.4.1` · **Size:** medium
**Created:** 2026-09-04 12:28:38 EDT · **Closed:** 2026-09-04 17:34:04 EDT
**Plan:** [202609/kill\_and\_edit\_last\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/kill_and_edit_last_landing_gaps.md)

## Description

resolved-consumption: keep the newest resolved launch target stable through prompt resolution and confirmation, consume it only when kill or dismissal initiation succeeds, and cover cancellation, resolution failure, duplicate presses, and single/bulk paths with regression tests.

## Notes

[2026-09-04T20:35:19Z · sase-w8.4.1] PROPOSED FOLLOW-UP: Split oversized link-follow action module — just check fails at lint/toobig because src/sase/ace/tui/actions/link_follow.py is 1066 lines over the 1000-line limit.

[2026-09-04T21:32:32Z · sase-w8.4.1] PROPOSED FOLLOW-UP: Fix unrelated stable full-suite failures — tests/ace/tui/widgets/test_agent_list_runtime_rendering.py expects nested monitor runtime 2m but gets 3m, and tests/ace/tui/test_proc_producer_inventory.py expects 43 production producers but sees 42.

[2026-09-04T21:34:04Z · sase-w8.4.1] Implemented resolved ,X pending-state consumption: record stays targetable on cancel, prompt or identity failure, and initiation refusal, then consumes on accepted single or bulk kill/dismissal. Verified focused launch/keymap suite 131 passed; shutdown tests 15 passed; just fmt; just _lint-symvision; just validate; core-floor advisory; validate-committed-plans; epic-symbols none. just check now fails only on unrelated toobig link_follow.py 1066>1000; test-scoped escalated to full suite and found unrelated stable failures recorded as proposed follow-ups.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w8.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w8.4.1/README.md) | [sase-w8.4.1](sase-w8.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a90ff8`](https://github.com/sase-org/sase/commit/5a90ff8826f51d6d4c363bf28944de81ec77bc4c) | fix(ace): delay last-launch record consumption | [sase-w8.4.1](sase-w8.4.1.md) | 2026-09-04 17:37:02 EDT |

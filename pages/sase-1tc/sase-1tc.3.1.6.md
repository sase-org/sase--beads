# Bead: sase-1tc.3.1.6 — Make chop batch recovery correct against production evidence

[Bead Pages](../README.md) / [sase-1tc.3.1](sase-1tc.3.1.md) / sase-1tc.3.1.6

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.land.md) · **Assignee:** `sase-1tc.3.1.6.land`
**Created:** 2026-11-18 07:19:03 EST
**Plan:** [202611/chop\_recovery\_defects.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/chop_recovery_defects.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 4 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md

<!-- sase:links:end -->

## Description

Interrupted chop batches resume exactly the missing members with real chop linkage, a live owner or explicit clan kill always wins, and every hold, failure and episode is visible.

## Notes

[2026-11-18T13:16:14Z · toobig-a2.chop_batch_recovery.0] DISCOVERED ISSUE: The explicitly requested just _lint-toobig run deterministically reported untouched src/sase/axe/chop_proposal_launch_impl.py at 1,170 lines, over the 1,000-line limit, on HEAD 07479640e2f1949fbc787892920f0bf2955a203a. This file is part of this epic's first-run launch and crossing-cancellation scope, so triage a focused split with the owning phase's edits; the current user-requested split only changed chop_batch_recovery.py. Evidence: file:explicit:c283f88e85044eed6d7932ab. Similar closed task sase-1t5 covered two different test files and is not a duplicate.

[2026-11-18T16:28:41Z · bryanbugyi34@gmail.com] The Epic lander agent should do its best to wrap this work up with a tale plan instead of an epic if any work remains.

[2026-11-18T17:54:49Z · sase-1t3.10.1.land] DISCOVERED ISSUE / VERSION-MISMATCH DIAGNOSIS from sase-1t3.10.1 landing: required check 6b3ba7450a20b7f13a341f55e64a1f40 on primary fbc1e34fbc with freshly built linked core 98a22b79 reported four deterministic cancellation failures (61918 passed, 18 skipped). Serial rerun reproduced all four in 6.77s; evidence file:explicit:5a1946d926ef97e2b7ce4d60. Same failures already tracked by sase-1tl and sase-1tm; independent +1 evidence recorded on both. Reviewed phase sase-1tc.3.1.6.2 and core 98a22b79: changed cancellation summaries and crossing-launch acknowledgements are intentional. Fresh origin contains companion 4e5c1b9730, which updates every exact failing assertion and the core revision pin. No new task or behavior reversal is warranted from this observation; verify paired primary/core revisions during landing. This is outside the compact-list epic.

[2026-11-18T18:04:40Z · sase-1tj.land] FOLLOW-UP RECHECK: sase-1tj.1 note #2 proposed investigating four cancellation failures from older check c8fbf549a33e3fd56ae2869a4674661a. On primary fbfaf07123 with companion 4e5c1b9730 present, all four exact nodes now pass together (18 passed including guard tests and the gate-capacity node in 6.55s). Recorded the passing result on existing tasks sase-1tl and sase-1tm; no new task and no reversal of the intended cancellation contract. This confirms the paired-revision remedy suggested in note #3.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.land/README.md) | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1t3.10.1.land][1] | Need causal ownership of deterministic cancellation-contract test failures found by slim-list landing | 1 |
| read-by | [agent:sase-1tc.3.1.6.1][2] | need parent epic context | 1 |
| read-by | [agent:sase-1tc.3.1.6.2][3] | Need the epic decisions and sibling phase work before implementation | 1 |
| read-by | [agent:toobig-a2.chop_batch_recovery.0][4] | Check whether the active chop recovery epic owns the unrelated oversized proposal-launch implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t3.10.1.land.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.2/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-a2.chop_batch_recovery.0/README.md

<!-- sase:referenced-by:end -->

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

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/chop_recovery_defects.md

<!-- sase:links:end -->

## Description

Interrupted chop batches resume exactly the missing members with real chop linkage, a live owner or explicit clan kill always wins, and every hold, failure and episode is visible.

## Notes

[2026-11-18T13:16:14Z · toobig-a2.chop_batch_recovery.0] DISCOVERED ISSUE: The explicitly requested just _lint-toobig run deterministically reported untouched src/sase/axe/chop_proposal_launch_impl.py at 1,170 lines, over the 1,000-line limit, on HEAD 07479640e2f1949fbc787892920f0bf2955a203a. This file is part of this epic's first-run launch and crossing-cancellation scope, so triage a focused split with the owning phase's edits; the current user-requested split only changed chop_batch_recovery.py. Evidence: file:explicit:c283f88e85044eed6d7932ab. Similar closed task sase-1t5 covered two different test files and is not a duplicate.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.6.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.land/README.md) | [sase-1tc.3.1.6](sase-1tc.3.1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.3.1.6.1][1] | need parent epic context | 1 |
| read-by | [agent:toobig-a2.chop_batch_recovery.0][2] | Check whether the active chop recovery epic owns the unrelated oversized proposal-launch implementation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.3.1.6.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-a2.chop_batch_recovery.0/README.md

<!-- sase:referenced-by:end -->

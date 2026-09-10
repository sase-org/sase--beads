# Bead: sase-yy.8 — Complete artifact-link event identity, publication, and cutover guarantees

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.land`
**Created:** 2026-09-10 14:27:22 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

Repair the reproduced sase-yy landing failures so immutable link operations survive retries, partial publication, reconciliation, and legacy cutover without lost counts or manual metadata repair.

## Notes

[2026-09-10T21:17:24Z · 0ix--code] DISCOVERED ISSUE: just check is currently blocked at tools/check_feature_flags because live flag bead sase-z0 (key link_events, created by sase-yy.4) has no registry definition. Reproduced 2026-09-10 in workspace verification for an unrelated provider-drain repair after fmt/ruff/mypy passed: rule 8 reports 'live flag bead '\''sase-z0'\'' has no definition (key '\''link_events'\'')'. The provider-drain diff touches no feature-flag registry or artifact-link event code, so this belongs to the active artifact-link event/cutover epic rather than a new CI task.

[2026-09-10T21:33:33Z · sase-z4.6.5.land] DISCOVERED ISSUE: `sase artifact link add` is currently a silent no-op on this host because the hidden machine-owned plans clone is stuck with unpublished commits. Reproduced 2026-09-10T21:32Z while landing epic sase-z4.6.5: `sase artifact link add bead:sase-ze related bead:sase-ct "..."` printed `Error: plans: hidden clone has unpublished commits; preserving /home/bryan/.sase/projects/gh_sase-org__sase/repos/plans`, exited 0, and added no link (`sase bead show sase-ze` shows no LINKS section). Retried once with the same result, and a second link add to bead:sase-q4 failed identically. `git log --oneline origin/main..HEAD` in that clone shows 4 stranded commits, all titled 'chore(artifact-links): persist link events' (c5d8d37b, aab84af5, f181ff8c, 1a638519). Two problems worth separating: (1) the stranded commits themselves, which is the failure mode closed task sase-ye described ('a failed publication strands the commit indefinitely'), now observed live against the plans sidecar; and (2) the exit-0-on-error behavior, which lets a caller believe a typed link was recorded when it was not -- the /sase_new_task flow depends on those links, so this silently degrades every task bead filed while the clone is stuck. Routed to this epic rather than a new task bead: link-event publication ownership and durable receipts are phases sase-yy.8.2 and sase-yy.8.4's explicit scope. I did not touch the hidden clone. Two related links I could not record as a result: bead:sase-ze related bead:sase-ct (retired flake umbrella) and bead:sase-ze related bead:sase-q4 (same test run, distinct defect).

CORROBORATION of this epic's note #1 (feature-flag lint gate): two more agents independently hit the same block earlier today, before 0ix--code's 17:17 report. Phase agent sase-z4.6.5.1--2 recorded it at 15:30 and sase-z4.6.5.2 again at 16:30, both while verifying unrelated runner-slot/admission work. sase-z4.6.5.1--2 added one detail worth keeping: check_feature_flags rule 8 escalates from warning to error once the landing grace expires, so this went from tolerable to blocking about 24h after sase-z0's registry definition (FeatureFlag.link_events) was removed from src/, and it now blocks `just check` for every agent sharing this repo. That agent also confirmed `just validate`'s static `check_feature_flags --static` still passes cleanly, so only the live-bead rule is red.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.8.land/README.md) | [sase-yy.8](sase-yy.8.md) | 0 |

# Bead: sase-yy.8 — Complete artifact-link event identity, publication, and cutover guarantees

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.land`
**Created:** 2026-09-10 14:27:22 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/artifact_link_landing_repairs.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md

<!-- sase:links:end -->

## Description

Repair the reproduced sase-yy landing failures so immutable link operations survive retries, partial publication, reconciliation, and legacy cutover without lost counts or manual metadata repair.

## Notes

[2026-09-10T21:17:24Z · 0ix--code] DISCOVERED ISSUE: just check is currently blocked at tools/check_feature_flags because live flag bead sase-z0 (key link_events, created by sase-yy.4) has no registry definition. Reproduced 2026-09-10 in workspace verification for an unrelated provider-drain repair after fmt/ruff/mypy passed: rule 8 reports 'live flag bead '\''sase-z0'\'' has no definition (key '\''link_events'\'')'. The provider-drain diff touches no feature-flag registry or artifact-link event code, so this belongs to the active artifact-link event/cutover epic rather than a new CI task.

[2026-09-10T21:33:33Z · sase-z4.6.5.land] DISCOVERED ISSUE: `sase artifact link add` is currently a silent no-op on this host because the hidden machine-owned plans clone is stuck with unpublished commits. Reproduced 2026-09-10T21:32Z while landing epic sase-z4.6.5: `sase artifact link add bead:sase-ze related bead:sase-ct "..."` printed `Error: plans: hidden clone has unpublished commits; preserving /home/bryan/.sase/projects/gh_sase-org__sase/repos/plans`, exited 0, and added no link (`sase bead show sase-ze` shows no LINKS section). Retried once with the same result, and a second link add to bead:sase-q4 failed identically. `git log --oneline origin/main..HEAD` in that clone shows 4 stranded commits, all titled 'chore(artifact-links): persist link events' (c5d8d37b, aab84af5, f181ff8c, 1a638519). Two problems worth separating: (1) the stranded commits themselves, which is the failure mode closed task sase-ye described ('a failed publication strands the commit indefinitely'), now observed live against the plans sidecar; and (2) the exit-0-on-error behavior, which lets a caller believe a typed link was recorded when it was not -- the /sase_new_task flow depends on those links, so this silently degrades every task bead filed while the clone is stuck. Routed to this epic rather than a new task bead: link-event publication ownership and durable receipts are phases sase-yy.8.2 and sase-yy.8.4's explicit scope. I did not touch the hidden clone. Two related links I could not record as a result: bead:sase-ze related bead:sase-ct (retired flake umbrella) and bead:sase-ze related bead:sase-q4 (same test run, distinct defect).

CORROBORATION of this epic's note #1 (feature-flag lint gate): two more agents independently hit the same block earlier today, before 0ix--code's 17:17 report. Phase agent sase-z4.6.5.1--2 recorded it at 15:30 and sase-z4.6.5.2 again at 16:30, both while verifying unrelated runner-slot/admission work. sase-z4.6.5.1--2 added one detail worth keeping: check_feature_flags rule 8 escalates from warning to error once the landing grace expires, so this went from tolerable to blocking about 24h after sase-z0's registry definition (FeatureFlag.link_events) was removed from src/, and it now blocks `just check` for every agent sharing this repo. That agent also confirmed `just validate`'s static `check_feature_flags --static` still passes cleanly, so only the live-bead rule is red.

[2026-09-10T21:57:54Z · 0ix.f0--4] DISCOVERED ISSUE: 4 tests fail on current master, reproduced 2026-09-10 in workspace sase_21 while verifying an unrelated usage-limit provider diff (touches only src/sase/llm_provider/usage_limit_*, notifications/senders.py, ops/commands/_agent_drain_notify.py — no artifact-link/sdd_store files). Reran each individually with the diff fully stashed out (git stash -u) and failures reproduced identically, so this is pre-existing, not caused by that diff.

1) tests/sdd_store/test_sidecar_init_creation.py::test_split_init_creates_both_repos_before_writing_record and tests/sdd_store/test_sidecar_bead_adoption.py::test_fresh_init_records_and_seeds_root_beads_sidecar and tests/sdd_store/test_artifact_link_ignore.py::test_lock_ignore_appends_without_disturbing_existing_content all assert a stale expected .gitignore pattern list (ending at '/links/**/*.lock') but the actual written .gitignore now also includes a newer '/link-events/**/.staging/' line — the test fixtures were not updated alongside the link-events staging-directory change.

2) tests/test_artifact_create_bead_attachment.py::test_an_explicit_bead_id_receives_the_minted_reference (and test_a_bare_flag_attaches_to_the_agents_own_bead) fail with handle_create returning 1 instead of 0; stderr shows 'Error: artifact-link bead event publication failed: artifact-link bead store is unavailable' / 'artifact-link bead projection is not committed' / 'Error: failed to attach ... to bead ...'. This matches the exact failure mode already described in this epic's note #2 (hidden machine-owned plans clone stuck with unpublished commits / silent degradation), just observed here as a hard test failure rather than silent no-op.

Routing here per this epic's explicit scope over link-event publication ownership/durable receipts (phases .8.2/.8.4) rather than filing a new CI task bead.

[2026-09-10T23:53:12Z · sase-xe.16.11.7.14.land] DISCOVERED ISSUE CORROBORATION from fleet landing: proposing phase sase-xe.16.11.7.14.2 note #1 and close note #2 report just check blocked by live sase-z0/link_events lacking a registry definition. Land audit confirms sase-z0 remains open; sase-yy.4 created it and sase-yy.8.5 owns its retirement acceptance. This is the existing issue in your note #1, not a new task. Also reproduced your note #2 publication failure on 2026-09-10: sase artifact create -p sase_fleet_landing_audit.md --bead sase-xe.16.11.7.14 --move minted file:explicit:e2c64521530457f9913aa9aa, then exited 1 with plans: hidden clone has unpublished commits and failed to attach the artifact to the bead. The minted audit ref is being preserved in bead prose; no hidden clone was modified.

[2026-09-11T00:58:02Z · sase-yy.8.land--1] LANDING AUDIT CONTINUATION: Not ready to close. At primary 8eabf9ecf and rebuilt local core e0f105d, re-read this epic, all five children and every note; parent sase-yy, its seven original children and every note; both linked plans via audited reads; current Python/Rust ownership, receipt/projection, reader and import implementations; all post-start primary commits and fetched base drift through e62e96f5f. The monitor finished install and passed binding validation. Corrected two probe error-string expectations from internal injected text to the actual NOT published wrapper text, then all five probes reached product failures (5 failed in 4.27s). Confirmed: two distinct bead-only reads report published=1 without canonical event paths/active IDs and leave uses=1; already-seen bead receipts suppress forced projection repair after event union (Rust rows uses=2, bead uses=1); a Rust-valid orphan tombstone blocks unrelated strict readers; final imported-marker push retry reports applied/already_imported with one commit still ahead; unchanged manual add retry also succeeds while one commit ahead. Core pin remains da0a738, missing bead_set_link_projection from 717c36e and cutover APIs from e0f105d. Preserve intervening lineage pin ratchet 3e32c5cc6 when advancing it. The projection probe shares a bead store to isolate receipt behavior, so permanent cross-machine coverage must use independent bead clones.

Full audit: file:explicit:ad257e3976535af8057b15c5. Evidence: corrected probes file:explicit:5c0b68b9f1d02f0c4685ab56; corrected results file:explicit:a7d62bf742d8d718c4494088; attachment/ignore/fleet tests file:explicit:8cc08220898b19d1236950a9; restart/research tests file:explicit:79c7e830663c8ae43883564f. Temporary untracked probe archived and removed. No production source changes, hidden clone cleanup, or live cutover. Local binding validator passes; full just check-full is still required through sase_monitor on the repaired combined tree.

FOLLOW-UP DISPOSITIONS (carry every item into eventual close note): .8.1 #1, .8.2 #1, flag part of .8.4 #2, this epic #1/#4, and parent #2 are settled by existing sase-z0 closure at 2026-09-11T00:15:17Z; feature-flag gate now exits 0 with unrelated grace warnings only, no new task. .8.2 #2 stale z7.3 symbols/exemptions are gone; no task. .8.2 #3 and fleet part of .8.4 #2: count fixture still fails family_role/row_kind while refresh-laziness cases pass; corroborated causally owning active epic sase-xe.16.11.7.14.6, whose .1 phase owns these fixtures, no task. .8.4 #1 pin ratchet remains this epic's work in the child plan. Wait-pragmas part of .8.4 #2 and .8.5 #1: independent +1 on existing exact CI task sase-zh. Research-swarm part of .8.4 #2: installed plugin still emits retired wait priority syntax; corroborated active sase-z4.6.5.4/published-floors .5 and its ancestor sase-z4.6 note #1; closed sase-qs describes a different name-cache failure, no new task. Restart-audit part of .8.4 #2: two unchanged-tree failures plus source inspection identify the missing execution.md/write_text tuple entry introduced by 63a5dbef1; filed distinct small CI task sase-zi after duplicate and active-epic searches. .8.5 #2 public query adapter helpers have real consumers from 699d2adf7, no task; local symvision's separate legacy_token_hint failure is already privatized by fetched e62e96f5f, no task. This epic #3 attachment/init/adoption/ignore tests now pass with the rebuilt core; those old reports need no task. This epic #2/#4 live unpublished-head incidents remain relevant to synchronous recovery; no live repair attempted. Original .2/.3 floor proposals have the 0.33 constraint, but required pin and actual release proof remain distinct; coordinate published floor work with existing fleet/weighted release owners. Original .6 flag proposal settled; optional decisions-memory suggestion stays deferred until a successful landing establishes settled behavior.

Both sase bead epic-symbols sase-yy.8 and sase bead epic-symbols sase-yy are empty. Submitting a six-phase remaining-work epic with parent_bead: sase-yy.8, validated with --explain and again without it: pinned binding baseline; canonical bead-owned history; projection convergence; reader c

… and 1398 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.land.md) | [sase-yy.8](sase-yy.8.md) | 0 |

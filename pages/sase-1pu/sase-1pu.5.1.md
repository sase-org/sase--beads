# Bead: sase-1pu.5.1 — Published agent run state convergence

[Bead Pages](../README.md) / [sase-1pu.5](sase-1pu.5.md) / sase-1pu.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.md) · **Assignee:** `sase-1pu.5.1.land`
**Created:** 2026-10-29 20:35:51 EDT · **Closed:** 2026-11-01 14:11:23 EST
**Plan:** [202610/published\_run\_state\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202610/published_run_state_convergence.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/published_run_state_convergence.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 5 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/published_run_state_convergence.md

<!-- sase:links:end -->

## Description

Make published agent runs converge to verified terminal state without regressing newer snapshots or treating live runs as finished.

## Notes

[2026-10-30T10:23:32Z · toobig-8u.reclaim.0--1] DISCOVERED ISSUE: The standalone just _lint-toobig run during the gate-turn reclaim split failed on src/sase/agents_sync/publication_state_repair.py at 1,784 lines (limit 1,000). This is outside the split; the new reclaim modules are 21/481/294/3 lines. The oversized repair module falls within this active published-run-state convergence epic's code area; consider splitting it during the remaining landing work. Evidence: file:explicit:0dbeaffa58185dbdc6374ece.

[2026-11-01T15:09:38Z · sase-1pu.5.1.land] LAND FOLLOW-UP TRIAGE (2026-11-01, reviewed HEAD 5036f01eb2): reviewed every note on phases sase-1pu.5.1.1-.4 and the epic note. Used /sase_new_task, searched all task statuses, swept the last week of tasks, and reviewed the active epic catalog.
1. sase-1pu.5.1.2 note 1 (missing tests._agent_artifact_marker_audit_helpers in test_scoped_run_ignores_parent_shard_spec): DECLINED as already fixed by 86bec79ca4. The exact node passes now; the 42-test publication/state-refresh/scoped-node group passed in 21.95s. No matching unresolved task exists, so no duplicate or new task was filed.
2. sase-1pu.5.1.3 note 1 (unobserved full just check pass / monitor timeout): DECLINED as a separate task; this is historical verification debt, retained in the remaining-work acceptance. ToolRun d437d7ae882a5d2031516fc1c0087ddc eventually completed failed/1 after 216m, rather than proving a pass. Its NEW missing-helper and completion-snapshot failures are fixed on this tree: exact scoped node passes and completion snapshot/kind suites pass 11/11 in 4.45s. Other items were KNOWN/FLAKY in the ToolRun. The core-floor advisory is superseded: current pin 764317b9 contains the state-policy commit 7de361cc. No current distinct infrastructure defect was reproduced. Tasks sase-1pv (foreground handoff) and sase-1pw (worker-token starvation) were inspected but are not corroborated by these already-monitored, single-worker runs.
3. sase-1pu.5.1.4 note 2 (one-hour check timeout): DECLINED as a separate task for the same reason. ToolRun 434baebbc86f1c6ceed388e12ccae615 records signaled/undetermined, stop_requested, not a passing check or a diagnosed product failure. The coder must obtain current just check evidence; no check-full is authorized.
4. Epic note 1 (1,784-line repair module): ADDRESSED by cf68c745f1; task sase-1q1 is already closed with that evidence. Keep the split modules. Historical phase epic-symbol close blockers were removed by landed commits; one parent exemption remains for AgentRunStateProjectCheckpointWire and is explicit remaining closeout work.
No new task beads or +1 votes were appropriate. These outcomes must be included in the final close note. Existing real product defects identified below remain this epic's work. Process gates and completed test runs are not a substitute for fixing them.

[2026-11-01T15:10:08Z · sase-1pu.5.1.land] LAND AUDIT / REMAINING WORK (2026-11-01, HEAD=origin/master=5036f01eb2): reviewed all four closed phases and notes, plan:202610/published_run_state_convergence.md and parent plan, inherited optional_scope=keep_five_seeds, Rust commit 7de361cc and Python commits 1d1c46262a / 5c14ac6a54 / b1618348d4. Current sase-core pin 764317b9 descends from 7de361cc. Core resolve/window/schedule policies and registered binding tests exist; current Python focused suite is 42/42 plus completion suites 11/11. These tests inject InventoryRun loaders and therefore do not establish real marker-read acceptance.
Confirmed blockers: (a) inventory_sources._artifact_state treats {} and {outcome: unknown} as failed, and ignores a conflicting done.name; an actual stopped outcome is also mapped to failed. Inventory must feed validated exact-run observations to the Rust policy, retaining unknown/conflicting evidence. (b) _publication_state_repair_evidence.default_inventory_loader still calls build_project_hood_inventory, which loads project commit history and prompt/chat/embedded/prompt-step payloads for all runs in selected hoods; it has no selected-run input. Repair's run limit does not bound those reads. collect_published_rows also walks every snapshot without the work deadline; normal page planning verifies all content files in changed hoods. (c) direct probe: deadline=0 with one selected active run and completed evidence returns examined=1, failed=1, changed=0, next_cursor present, pass_complete=true, error=None. A corrupt owner manifest returns failed=0/pass_complete=true. _push_ahead_convergence swallows unreadable ahead-state errors. The scheduler interprets these false-success reports as progress. (d) resolve_preserved_run_state catches a Rust validation error and returns the candidate; direct probe with published completed/invalid historical timestamp and candidate active returns active while diagnostic says unchanged. Preserve the published fields on unresolvable same-run merges.
Integration reviewed: background enqueue/drain (4356cffaa1/e69360f49d/6d615680b8), state job fixes (86bec79ca4), module/test splits, scan reuse (30e012baaa), planner linked scopes/archive restore/scope repair (9409312d1e/f1dcab6dae/4900d9a0f3). Existing publication still passes through the shared snapshot builder, and CLI repair modes are mutually exclusive. Retain the job pre-charge/backoff and protection reuse; add regression coverage for later publishers using terminal preservation. docs/contribute/agents-sidecar-sync.md still describes immediate commit drains despite the background enqueue switch; correct that paragraph during integration.
Preparing a medium tale for one coder to fix the Python observation/repair orchestration using the existing Rust policy and indexed lookup APIs, add production-path evidence tests, clear the checkpoint symbol, verify, and close this epic plus only parent phase sase-1pu.5 in the same turn as final code. Do not close sase-1pu or seed sase-1cc. Epic remains open because the original acceptance is not yet met.

[2026-11-01T15:15:27Z · sase-1pu.5.1.land] LAND PLAN SIZING UPDATE: completing the backend-boundary review changed the tentative medium-tale choice in the preceding audit note. The existing Rust binding accepts preclassified terminal_marker/evidence_state values; raw marker classification still happens in Python, and bounded hood discovery needs a cursor-aware core contract so empty/corrupt units can make progress without loading every snapshot. The remaining work therefore needs two dependent medium phases: core evidence/discovery contracts first, then Python adapters/production-read tests and the containing core pin. A single tale cannot consume its own host-created core SHA before its turn ends. The child epic parent_bead is sase-1pu.5.1; parent closeout is left to its lander, not a phase. The Python phase retires the parent checkpoint exemption before its own commit, so the later lander can pass the existing local+upstream symbol guard without waiting for its own commit. The plan passed validate --explain and a second validation without --explain, with no warnings. Follow-up triage is already recorded above; no additional follow-up remains untriaged.

[2026-11-01T17:54:37Z · sase-1pu.5.1.5.land] CHILD LANDING BLOCKER: sase-1pu.5.1.5 landing at a0b00da79b reproduced unfinished exact-run identity and bounded-read contracts despite 47 focused passes: stale cached artifact IDs and overwritten metadata conflicts can terminalize the wrong run; dismissed lookup rebuilds or misses agent_name != cl_name and trusts stale bundle identity; page planning re-reads unselected prompts/all snapshots; deadline crossing on last evidence read still advances. Details and reproducer file:explicit:ed35fecafbc1e54897ae808e are on child epic. A medium remaining-work tale includes fixes plus child/parent-plan/phase closeout; this parent stays open until actual acceptance and descendant/plan readiness are rechecked.

[2026-11-01T19:11:23Z · sase-1pu.5.1.5.land] Rechecked parent plan sase-1pu.5.1 after closing child epic sase-1pu.5.1.5. Descendants: original phases .1–.4 closed; child epic sase-1pu.5.1.5 and its phases .1/.2 closed. Linked plan:202610/published_run_state_convergence.md acceptance now met: exact-run identity, bounded selected-run evidence, honest deadline/cursor freeze, terminal preservation, scheduled agent_state_refresh, and owner-local runbook. epic-symbols sase-1pu.5.1: none. Inherited optional_scope=keep_five_seeds. Core pin dc5383f6 preserved. Post-child origin/master drift 17d8fe5937/a19243cdf6/71827cfecc is gate-turn/staged-handoff with no publication overlap.

Verification: focused publication repair/targeted pytest 50 passed in 38.47s; just fix; just symvision green after child close; sase tool run check e1f6b07ae4b3cd6b69c3d9f10f78f10f 59580 passed / 17 skipped / 1 NEW sudo-ledger flake sase-1oy (serial pass, +1 recorded, touched=false).

Prior lander follow-up outcomes (sase-1pu.5.1 note 2): phase .2 note 1 missing miniature-repo helper declined as fixed by 86bec79ca4; phase .3 note 1 unobserved check/timeout declined as historical verification debt (ToolRun d437d7ae eventually failed; NEW helper/completion nodes now pass; sase-1pv/sase-1pw not corroborated); phase .4 note 2 one-hour check timeout declined (ToolRun 434baebb signaled/undetermined); epic note 1 oversized repair module addressed by cf68c745f1 and closed sase-1q1. Child lander follow-ups: phase sase-1pu.5.1.5.1 note 1 declined (dc119c0b + closed sase-1qk.1; evidence on sase-1pj.6.1); phase sase-1pu.5.1.5.2 note 1 +1 on sase-19m (ToolRun af92a91bfbe6635cd5c072966a9dc112). No new tasks.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.5.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.land.md) | [sase-1pu.5.1](sase-1pu.5.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:162][1] | Comparing phase bead sase-1pu.5.1 against epic sase-1pt to check for a conflict | 1 |
| read-by | [agent:sase-1pu.5.1.1--1][2] | Check the epic decisions governing this phase before close | 1 |
| read-by | [agent:sase-1pu.5.1.3--1][3] | epic decisions | 4 |
| read-by | [agent:sase-1pu.5.1.4--1][4] | Need parent epic decisions | 1 |
| read-by | [agent:sase-1pu.5.1.5.2][5] | Need DECISIONS section from truncated parent | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.162/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.1.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.3.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.1.4.md
[5]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.5.1.5.2/README.md

<!-- sase:referenced-by:end -->

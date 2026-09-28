# Bead: sase-1bf — Bound agent scratch by ownership, not by environment luck

[Bead Pages](../README.md) / sase-1bf

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.land`
**Created:** 2026-09-27 14:23:29 EDT · **Closed:** 2026-09-27 23:00:08 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/bounded_agent_scratch.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1bw][2] | Parent epic whose scratch-liveness phase (sase-1bf.2) introduced the fail-closed rule for unreadable post-birth processes; its landing tale adds the zombie exemption. |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1bw/README.md

<!-- sase:links:end -->

## Description

Per-launch agent scratch (cargo targets, agent TMPDIRs) is removed when its launch is dead, on every managed temp root any writer actually used, regardless of which environment the service host was started with; cleanup refusals are visible; and `sase disk list` / disk-pressure notifications account for where the bytes really are, so a SASE host can no longer silently fill its disk.

## Notes

[2026-09-27T22:27:53Z · sase-1b2.land] DISCOVERED ISSUE (sase-1b2.land, sase-core 924884e, rustc/clippy 1.98.1 stable): ./scripts/check.sh clippy is red on crates/sase_core/src/launch_scratch_liveness.rs, added by 297bc1e (sase-1bf.2). Line 300 fn observe_unreadable trips clippy::too_many_arguments (8/7) in the lib, and line 477 fields.extend(std::iter::repeat("0".to_string()).take(17)) trips clippy::manual_repeat_n in lib test. These are the only sase_core lib/lib-test clippy denies at HEAD (the earlier finalizer/run_view/decode.rs denies from sase-1b2 no longer fire). Distinct from umbrella sase-1an (manual_range_contains/nonminimal_bool in other files).

[2026-09-28T01:21:59Z · sase-1bf.land] LAND TRIAGE (sase-1bf.land, sase master 965248789b, sase-core bc71eb2). Outcome for every PROPOSED FOLLOW-UP and discovered issue:
- sase-1bf.1 #1 and sase-1bf.3 #2 (sase-core clippy drift in agent_runtime/agent_scan/decode/fleet_owner_facts/provider_usage/tool_run): duplicate of sase-1an. Corroborated with sase bead +1 (agent_runtime.rs:567 still flagged at bc71eb2). The launch_scratch_liveness.rs part (and epic note #1 from sase-1b2.land: too_many_arguments + manual_repeat_n) was caused by sase-1bf.2 and is already fixed upstream in sase-core bc71eb2 (sase-1bu.1). No action needed.
- sase-1bf.1 #2 (feature-flag lint closed_survives for sase-1b5 ace_final_deck): declined, already resolved. 2d8f2f0566 removed the flag, and tools/check_feature_flags passes at HEAD.
- sase-1bf.2 #3 (symvision usage_windows pragma symbols missing from sase-telegram): declined, no longer reproduces. just symvision at HEAD no longer reports it.
- sase-1bf.3 #3 and sase-1bf.4 #1 (symvision private import _segment_section_identity): declined, no longer reproduces at HEAD.
- sase-1bf.3 #4 (just check test-scoped escalated to FULL_SUITE and was killed after 1h): declined. The escalation is the intended src-data-asset rule for default_config/schema/docs edits, and the kill was the phase agent's own foreground tool timeout, not a SASE defect. Long-run handling is already tracked by sase-17g.
- sase-1bf.6 #1 (move sase-core-revision.txt past 90d141e): EPIC WORK, since sase master requires managed-tmp wire 4 and the pin 0e8981a builds wire 3. Done in the landing tale.
- sase-1bf.6 #2 (registry enrolled a per-launch agent-tmp/.../managed dir as a root): EPIC WORK. A root nested under another registered root double-counts bytes in sase disk list and gets reaped twice. The landing tale collapses nested roots in effective_managed_tmp_roots.
- sase-1bf.6 #3 (zombies and post-birth sshd sessions keep dead-launch entries incomplete): zombie part is EPIC WORK. A zombie holds no env or cwd, so the observer's false-incomplete is a sase-1bf.2 defect, and the landing tale skips Z/X-state pids. The live non-dumpable post-birth sshd part goes beyond the plan's explicit fail-closed rule and needs design work, so I filed sase-1bw (task(bug), large, ready) with a related link to this epic.
- sase-1bf.6 #4 (stale index.lock removed on athena's sase-core checkout): declined. It was a one-off operational recovery with no identified crashing process or reproducible defect, and no SASE task was found to own it.
- Discovered: just symvision at HEAD fails on rail_panel_title, rail_tooltip_text and rail_urgency (_agent_list_render_rail.py). Not caused by this epic; it is already recorded as a DISCOVERED ISSUE on the landing epic sase-1bn, so no new bead.

[2026-09-28T03:00:08Z · sase-1bf.land] Verified and closed per landing tale plan:202609/land_bounded_agent_scratch.md.

All six phases verified in source and commits: sase 40295eaf54 (sase-1bf.1), 7e4482a62f (sase-1bf.2), c2eb318d88 (sase-1bf.3), 5db68f77f2 (sase-1bf.4), d99f4789e9 (sase-1bf.5); sase-core 924884e (sase-1bf.1), 297bc1e (sase-1bf.2), 90d141e (sase-1bf.3). sase-1bf.6 host acceptance passed on apollo and athena.

Integration review: the only non-epic commit touching epic files, 965248789b, privatized unused registry and observation symbols without conflict. Epic note #1's clippy denies (too_many_arguments/manual_repeat_n in launch_scratch_liveness.rs) were fixed upstream in sase-core bc71eb2.

This tale's three fixes:
1. sase-core crates/sase_core/src/launch_scratch_liveness.rs: observe_launch_scratch_liveness now reads /proc/<pid>/stat state (via a new read_proc_stat helper shared with process_start_epoch, one read per pid) and skips Z/X (zombie/dead) processes outright instead of letting an unreadable environ/cwd mark the observation incomplete. Added zombie_process_is_not_counted_as_unreadable test; later_unreadable_process_stays_incomplete still passes for the non-zombie case. just test -p sase_core launch_scratch_liveness: 7/7 pass. just fmt clean. No new clippy deny in launch_scratch_liveness.rs (verified with cargo clippy -p sase_core --lib --tests -- -D warnings; the 9 pre-existing denies are all in agent_runtime.rs/provider_usage/receipt.rs/triage.rs, tracked by sase-1an). docs/axe.md updated.
2. sase src/sase/core/managed_tmp_roots.py: effective_managed_tmp_roots now folds a candidate whose resolved path sits strictly inside another candidate's resolved path into the outer root (Path.is_relative_to on resolved paths), after the existing resolved-path de-dup. Added 3 new tests (nested-root folding, sibling roots kept, /a/tmp vs /a/tmp2 not treated as nested); all 10 tests in test_managed_tmp_roots.py pass, all 10 in test_disk_footprint_inventory.py pass. docs/axe.md and docs/configuration.md updated.
3. sase-core-revision.txt: just ratchet-core-revision moved the pin 0e8981a1f131d2dd040c4887ae949edf19fbeef6 -> bc71eb2ca01667aa8eb907c2c94e72392cc5e40e (exit 2, bump applied, as expected). Confirmed sase-core 90d141e and 924884e are both ancestors of the new pin. tools/check_sase_core_rs_bindings reports sase_core_rs 0.35.1 exposes all 722 required bindings.

Verification results: sase tool run check (db269817c4f912574f05104c4e0a6782) — fmt/lint/symvision/SASE-validation/committed-plans all green. The sase-core-revision.txt change made test-scoped distrust its closure and escalate internally to the full suite (49034 passed), which is expected per docs/lint_and_test.md and is not a check-full run. The only symvision failures are the pre-existing rail_panel_title/rail_tooltip_text/rail_urgency trio owned by in-progress sase-1bn, as this plan anticipated. The full-suite escalation additionally surfaced ~23 further pre-existing failures, all traced to in-progress sase-1bn's agent-tab/rail refactor (agent completion candidates, directive completions, AgentList/header/palette widgets, ctx.agent_meta, a missing scoped_agents_for_owner import) or to two already-tracked unrelated task beads (sase-1bp: update-gear clock sites; sase-1as: getting-started Grok wording) plus one already-tracked epic (sase-1ah: sase.yml "receipt" field missing from the public schema). None touch managed-tmp/launch-scratch/disk-footprint files. Recorded as a DISCOVERED ISSUE note on sase-1bn, and corroborated sase-1bp/sase-1as with +1s; none required fixing here. Also ran the four focused suites named in the plan (test_managed_tmp_roots.py, test_disk_footprint_inventory.py, test_managed_tmp_reaper*.py, test_run_agent_runner_scratch_cleanup.py): 83/83 pass. sase bead epic-symbols sase-1bf: no entries.

Land agent's earlier triage note #2 pointer: sase-1an +1'd for the clippy-drift duplicate, new task sase-1bw filed for the live non-dumpable post-birth-sshd design work, and the remaining proposals (feature-flag lint, symvision usage_windows/private-import, FULL_SUITE escalation kill, stale index.lock) declined as already resolved, no-longer-reproducing, or one-off operational recovery with no owning defect.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1bf.1](sase-1bf.1.md) | Managed temp root registry the reaper follows | ✓ closed | medium | 2026-09-27 | 1 | 2 |
| [sase-1bf.2](sase-1bf.2.md) | Rust-owned launch scratch liveness that works under systemd | ✓ closed | medium | 2026-09-27 | 1 | 2 |
| [sase-1bf.3](sase-1bf.3.md) | Dead-launch backstop pass and liveness-aware pressure | ✓ closed | medium | 2026-09-27 | 1 | 2 |
| [sase-1bf.4](sase-1bf.4.md) | Truthful disk attribution under pressure | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bf.5](sase-1bf.5.md) | Retention for visual snapshot run reports | ✓ closed | small | 2026-09-27 | 1 | 1 |
| [sase-1bf.6](sase-1bf.6.md) | Integrated acceptance on apollo and athena | ✓ closed | small | 2026-09-27 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1bf: Bound agent scratch by ownership, not by environment luck [closed]"]
    n1["sase-1bf.1: Managed temp root registry the reaper follows [closed]"]
    n2["sase-1bf.2: Rust-owned launch scratch liveness that works under systemd [closed]"]
    n3["sase-1bf.3: Dead-launch backstop pass and liveness-aware pressure [closed]"]
    n4["sase-1bf.4: Truthful disk attribution under pressure [closed]"]
    n5["sase-1bf.5: Retention for visual snapshot run reports [closed]"]
    n6["sase-1bf.6: Integrated acceptance on apollo and athena [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n6
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.1.md) | [sase-1bf.1](sase-1bf.1.md) | 2 |
| [bbugyi200.apollo.sase-1bf.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.2.md) | [sase-1bf.2](sase-1bf.2.md) | 2 |
| [bbugyi200.apollo.sase-1bf.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.3.md) | [sase-1bf.3](sase-1bf.3.md) | 2 |
| [bbugyi200.apollo.sase-1bf.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.4.md) | [sase-1bf.4](sase-1bf.4.md) | 1 |
| [bbugyi200.apollo.sase-1bf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.5/README.md) | [sase-1bf.5](sase-1bf.5.md) | 1 |
| [bbugyi200.apollo.sase-1bf.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.6/README.md) | [sase-1bf.6](sase-1bf.6.md) | 0 |
| [bbugyi200.apollo.sase-1bf.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.land.md) | [sase-1bf](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d99f478`](https://github.com/sase-org/sase/commit/d99f4789e9c9bf2b49c6b76a77deb212da162389) | feat(visual): prune old screenshot maintenance run reports | [sase-1bf.5](sase-1bf.5.md) | 2026-09-27 14:37:05 EDT |
| sase | [`7e4482a`](https://github.com/sase-org/sase/commit/7e4482a62fe63645c36f73439d6abc79150837d4) | feat(scratch): rust-owned launch scratch liveness with systemd-safe probe | [sase-1bf.2](sase-1bf.2.md) | 2026-09-27 15:32:24 EDT |
| sase-core | [`sase-core@297bc1e`](https://github.com/sase-org/sase-core/commit/297bc1e3364c6017992b2307080390ae61894c8b) | feat(core): launch\_scratch\_liveness module with procfs probe bindings | [sase-1bf.2](sase-1bf.2.md) | 2026-09-27 15:35:48 EDT |
| sase | [`40295ea`](https://github.com/sase-org/sase/commit/40295eaf543f8e64e1e34c0862bce1411a353a42) | feat(managed-tmp): add Rust-owned root registry the reaper follows (sase-1bf.1) | [sase-1bf.1](sase-1bf.1.md) | 2026-09-27 17:19:10 EDT |
| sase-core | [`sase-core@924884e`](https://github.com/sase-org/sase-core/commit/924884e81b7c69aa2b30714a6cb2a9adac99484f) | feat(managed-tmp-roots): add Rust-owned registry with Py bindings (sase-1bf.1) | [sase-1bf.1](sase-1bf.1.md) | 2026-09-27 17:32:22 EDT |
| sase | [`5db68f7`](https://github.com/sase-org/sase/commit/5db68f77f2e46d989934643dd8dad318cbc13fa2) | feat(disk): truthful disk attribution under pressure (sase-1bf.4) | [sase-1bf.4](sase-1bf.4.md) | 2026-09-27 19:16:02 EDT |
| sase | [`c2eb318`](https://github.com/sase-org/sase/commit/c2eb318d8818f47390d80cfe8f07f5cd87cfe51e) | feat(managed-tmp): dead-launch backstop pass and liveness-aware pressure (sase-1bf.3) | [sase-1bf.3](sase-1bf.3.md) | 2026-09-27 19:39:41 EDT |
| sase-core | [`sase-core@90d141e`](https://github.com/sase-org/sase-core/commit/90d141eab03b28851bc1dd75762473967d057c13) | feat(managed-tmp): dead-launch backstop in Rust reaper wire (sase-1bf.3) | [sase-1bf.3](sase-1bf.3.md) | 2026-09-27 19:44:23 EDT |
| sase | [`241af2f`](https://github.com/sase-org/sase/commit/241af2fd8dec897b4596dcd9307fb08090df1cf7) | fix(managed-tmp): fold nested registered roots and ratchet the core pin | [sase-1bf](README.md) | 2026-09-27 23:05:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bf.1--a][1] | parent scope for phase close check | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.1.md

<!-- sase:referenced-by:end -->

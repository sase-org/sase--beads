# Bead: sase-sp — Make the commit declaration an authoring step, not a consent vote

[Bead Pages](../README.md) / sase-sp

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.land`
**Created:** 2026-08-24 09:19:07 EDT · **Closed:** 2026-08-24 16:11:13 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-t5][1] | The sase-sp epic phase sase-sp.5 proposed this follow-up; the epic shipped the consent model everywhere except protected core memory |

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-t5/README.md

<!-- sase:links:end -->

## Description

The finalizer declaration asks an agent only to author commit messages. Leaving a tree dirty becomes a rare, typed, host-adjudicated deferral that is corrected while the agent is still alive and never destroys a run.

## Notes

Check to make sure the 0cr sase agent didn't commit work that conflicts with this epic.

[2026-08-24T18:41:35Z · 0cq] DISCOVERED ISSUE: During unrelated Artifacts query-history implementation at HEAD f72ff9f38, just check escalated to the full pytest lane and failed tests/test_config_schema.py::test_default_config_matches_public_schema with finalizers.instances.commit.refusal: 'defer' is not one of ['fail']. Focused rerun reproduced the same schema error. The local diff does not touch src/sase/default_config.yml or config schema code; this appears causally tied to this epic's deferral/refusal-policy work, especially phase sase-sp.2's deferral config schema scope.

[2026-08-24T19:12:55Z · 0cw] DISCOVERED ISSUE: During unrelated Agents-tab mark navigation work at HEAD d88994bd8, just check failed at lint (symvision) after fmt, keep-sorted, ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and terminology gates passed. Failure is deterministic gate output from just _lint-symvision: unused public symbols AuthenticatedFinalizerPlan in src/sase/finalizers/plan.py plus configured_instance_from_json and configured_instance_to_json in src/sase/finalizers/config.py. My local diff only touches src/sase/ace/tui/actions/agents/_marking_navigation.py and tests/ace/tui/test_agent_marking.py, so this is unrelated to the mark-navigation tale. Routed here via /sase_new_task instead of creating a standalone task because active epic sase-sp owns finalizer declaration/refusal/config work and is a credible causal owner for public finalizer APIs left unused.

[2026-08-24T20:11:13Z · sase-sp.land] VERIFIED all six phases against source and commits (7b7452504, 570b6be4b, 524d8f26f, 45806495f, 2b046b174, 96675cd1a) plus the sase-core release. core: FinalizerDeferralReasonWire + Deferred statuses landed in sase-core afd1f87 and shipped as v0.31.12; the floor here is >=0.31.12,<0.32.0. adopt: config.py accepts fail|defer defaulting to fail, `sase final show` renders defer in yellow, and the inertness test exists. adjudicate: the free-text refuse action is gone repo-wide, declaration_deferrals.py adjudicates typed deferrals inside submit's lock against baseline + tool-call evidence. escape: `sase final defer` is registered (and present in the checked-in completion spec), an upheld deferral skips only its own stitch, aggregate rank makes deferred non-failing, and finalize_runner_shutdown holds the workspace with a "deferred commit" reason plus a notification naming repo/reason/paths and the manual `sase stitch create`. consent: commit_declaration evidence ships in final context and the recovery prompt's "do not mutate repositories" contradiction is gone. acceptance: all nine historical refusals are fixtures (5 unrepresentable, 2 rejected with counter-evidence, 2 upheld), FINALIZER_DEFERRALS telemetry has no duplicate catalog key, docs are synchronized, and sase-sd is closed as superseded.

INTEGRATED the 22 non-epic commits that landed since 7b7452504 and repaired both real seams. (1) The epic's own defect reported as a DISCOVERED ISSUE by 0cq: 2b046b174 flipped default_config.yml to `refusal: defer` but left src/sase/config/sase.schema.json pinned to enum ["fail"], breaking test_default_config_matches_public_schema and every schema-driven config surface (ACE config hub via axe_config_actions/_backend.py and `sase config` via axe/config_backend.py both load that schema). Added `defer` to the enum, corrected the description and the shipped instances default block, and pinned it with a new test_config_schema_accepts_both_finalizer_refusal_policies regression test. (2) The symvision gate broken by non-epic finalizer commit 43f4538f8, routed here by 0cw and separately filed as sase-t4: privatized AuthenticatedFinalizerPlan (only named inside plan.py; controller.py and executor.py reach it by attribute access through the still-public authenticate_resolved_finalizer_plan_full), deleted its dead agent_meta_projection method, privatized configured_instance_to_json/from_json, and dropped all three from their __all__ lists; sase-t4 is closed. Also closed the phase-4/phase-5 seam: /sase_final described the deferrals array but never named `sase final defer` nor stated what an upheld deferral does, so the skill source now says the tree stays dirty and the run completes as deferred, and names the command. Reviewed 901245cf3 (the out-of-band commit-obligation text) as complementary rather than conflicting: it adds a scope rule, not the consent rule.

FOLLOW-UPS from child PROPOSED FOLLOW-UP notes. sase-t5 (new, memory, small): publish the commit-by-default consent rule in core memory sase.md — sase-sp.5's proposal, still open because editing the protected template needs explicit user permission that neither the plan nor a host prompt can grant; linked related to this epic. sase-t6 (new, flake, large): test_snapshot_includes_live_config_token_refresh_threads flaked once for sase-sp.6 under heavy contention, passes in isolation on ad9ed74af; linked related to sase-j7. sase-t4 (existing, bug): closed, fixed above. sase-sp.3's and sase-sp.4's chezmoi memory-mirror / init memory --check drift proposals were DECLINED as no longer reproducible — `sase init memory --check` and the SASE validation gate are both green. sase-sp.6's completion-spec drift proposal was DECLINED for the same reason: tests/completion/test_snapshot.py passes, since the snapshot was regenerated by later commits; only its config-schema half was real and is fixed here.

VERIFICATION: `just check` green end to end on the combined tree — every whole-repo lint gate plus a scoped lane that escalated to the full suite (rules: src-data-asset). `sase bead epic-symbols sase-sp` reports no entries; the only --epic-symbol line left in the Justfile is sase-n4's, whose epic is still open.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-sp.1](sase-sp.1.md) | Typed deferral and a non-failing refusal policy in Rust core | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.2](sase-sp.2.md) | Adopt the released core floor and the deferral config schema | ✓ closed | small | 2026-08-24 | 1 | 1 |
| [sase-sp.3](sase-sp.3.md) | Adjudicate deferrals at submit time instead of after the turn | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.4](sase-sp.4.md) | A deliberate deferral escape hatch that does not fail the run | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.5](sase-sp.5.md) | Publish the commit consent model where agents actually read it | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.6](sase-sp.6.md) | Historical regression corpus, live acceptance, telemetry, and docs | ✓ closed | medium | 2026-08-24 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-sp: Make the commit declaration an authoring step, not a consent vote [closed]"]
    n1["sase-sp.1: Typed deferral and a non-failing refusal policy in Rust core [closed]"]
    n2["sase-sp.2: Adopt the released core floor and the deferral config schema [closed]"]
    n3["sase-sp.3: Adjudicate deferrals at submit time instead of after the turn [closed]"]
    n4["sase-sp.4: A deliberate deferral escape hatch that does not fail the run [closed]"]
    n5["sase-sp.5: Publish the commit consent model where agents actually read it [closed]"]
    n6["sase-sp.6: Historical regression corpus, live acceptance, telemetry, and docs [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n5
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.1/README.md) | [sase-sp.1](sase-sp.1.md) | 1 |
| [bbugyi200.athena.sase-sp.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sp.2.md) | [sase-sp.2](sase-sp.2.md) | 1 |
| [bbugyi200.athena.sase-sp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.3/README.md) | [sase-sp.3](sase-sp.3.md) | 1 |
| [bbugyi200.athena.sase-sp.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sp.4.md) | [sase-sp.4](sase-sp.4.md) | 1 |
| [bbugyi200.athena.sase-sp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.5/README.md) | [sase-sp.5](sase-sp.5.md) | 1 |
| [bbugyi200.athena.sase-sp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.6/README.md) | [sase-sp.6](sase-sp.6.md) | 1 |
| [bbugyi200.athena.sase-sp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.land/README.md) | [sase-sp](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@afd1f87`](https://github.com/sase-org/sase-core/commit/afd1f872ae785bac21cce97c4b8b85f24ebb82f7) | feat(finalizer): add typed deferral reason and non-failing Deferred status | [sase-sp.1](sase-sp.1.md) | 2026-08-24 09:33:11 EDT |
| sase | [`7b74525`](https://github.com/sase-org/sase/commit/7b74525044362eaee944f3dbe79474dc35eec651) | fix(finalizer): speak core finalizer wire v2 and decouple the plugin envelope | [sase-sp](README.md) | 2026-08-24 10:56:50 EDT |
| sase | [`570b6be`](https://github.com/sase-org/sase/commit/570b6be4b0c12eec328e1b8c66ac1440672fd81a) | feat(finalizers): raise sase-core-rs floor and wire FinalizerDeferralWire | [sase-sp.2](sase-sp.2.md) | 2026-08-24 11:01:09 EDT |
| sase | [`524d8f2`](https://github.com/sase-org/sase/commit/524d8f26f2b3ff619132248135ef2322349463c5) | feat(finalizers): adjudicate typed deferrals at submit time | [sase-sp.3](sase-sp.3.md) | 2026-08-24 12:12:14 EDT |
| sase | [`4580649`](https://github.com/sase-org/sase/commit/45806495fa3905e8d279f1bc504a24a9f02461e2) | feat(final): publish commit declaration consent model | [sase-sp.5](sase-sp.5.md) | 2026-08-24 12:50:15 EDT |
| sase | [`2b046b1`](https://github.com/sase-org/sase/commit/2b046b17460b2e86e24a157c1ba54a97549fd06a) | feat(finalizers): defer commit on refusal instead of failing the turn | [sase-sp.4](sase-sp.4.md) | 2026-08-24 13:22:05 EDT |
| sase | [`96675cd`](https://github.com/sase-org/sase/commit/96675cd1aa8641dd4aa9f0cd4d112c2b1723adfb) | test(finalizers): add historical refusal regression corpus and deferral telemetry | [sase-sp.6](sase-sp.6.md) | 2026-08-24 15:25:22 EDT |
| sase | [`6a91ae8`](https://github.com/sase-org/sase/commit/6a91ae88e2d1381105bf86d48c46924701a13e81) | fix(finalizers): accept refusal defer in the public config schema and privatize unused finalizer symbols | [sase-sp](README.md) | 2026-08-24 16:14:47 EDT |

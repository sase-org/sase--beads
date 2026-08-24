# Bead: sase-sp — Make the commit declaration an authoring step, not a consent vote

[Bead Pages](../README.md) / sase-sp

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.land`
**Created:** 2026-08-24 09:19:07 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Description

The finalizer declaration asks an agent only to author commit messages. Leaving a tree dirty becomes a rare, typed, host-adjudicated deferral that is corrected while the agent is still alive and never destroys a run.

## Notes

[2026-08-24T14:57:41Z · bryanbugyi34@gmail.com] SEQUENCING DEFECT FOUND AND UNBLOCKED (out-of-band fix on master).

Every agent launch on this host died before reaching the model with:

    Step 'main' failed: FinalizerPlanError: invalid finalizer plan:
    unsupported finalizer plan input schema_version 1; expected 2

Cause: phase `core` (sase-sp.1) bumped FINALIZER_WIRE_SCHEMA_VERSION 1 -> 2 in
sase-core (afd1f87) and closed, but the crate release its own plan step called
for ("Release the crate so this repo can pin a floor") is still an unmerged PR,
sase-core#173 / v0.31.12. Meanwhile every dev and host install of sase builds
sase_core_rs editable from the local sase-core checkout, by design -- the
Justfile says dev installs "build from sase_core_dir regardless", and the
sase_core_rs.pth in each venv points straight at the checkout. So the host
started speaking wire v2 the instant afd1f87 landed, while this repo still
stamped v1 on every plan input, and sase.finalizers.plan.resolve_and_persist_
finalizer_plan rejected it (Rust raise site: finalizer/selection.rs:388 via
validate_schema(input.schema_version, "plan input")).

The same skew made the tree red, not just the launcher: tests/test_core_
finalizer_facade.py and seven other finalizer suites failed, and
tools/validate_sase_core_rs reported "got 2, expected 1".

The plan's release-gated handoff (core releases -> adopt raises the floor) is
correct for consumers that install the published wheel, but local installs
never do. That leaves the whole host unlaunchable for the entire window
between the core bump landing and this repo adopting it, and phase `adopt` is
parked on a monitor polling PyPI for a release that has not merged, so the
window has no upper bound. Any future core wire bump repeats this unless the
bump and this repo's adoption land together, or the checkout-built path is
allowed to tolerate the skew. Worth a plan amendment before `adjudicate`,
`escape`, and `acceptance` touch the same wire.

Unblocked on master in 7b7452504: this repo now stamps wire v2, so launches and the
finalizer suites pass against the checkout-built core. Details and the
remaining adopt work are noted on sase-sp.2.

[2026-08-24T15:55:42Z · 0ch] DISCOVERED ISSUE: During unrelated pool-launch-reservation verification on 2026-08-24, the full just test-scoped lane and an immediate isolated rerun both failed tests/test_core_finalizer_facade.py::test_finalizer_facade_round_trips_deferred_instance_result. Reproduction: .venv/bin/python -m pytest tests/test_core_finalizer_facade.py::test_finalizer_facade_round_trips_deferred_instance_result -q. Failure: aggregate_finalizer_outcomes raises ValueError: instance 'commit' deferred status requires a terminal attempt when passed FinalizerInstanceResultWire(status='deferred', deferral=FinalizerDeferralWire(...), attempts=[]). This is unrelated to the LLM pool-reservation diff and is credibly in this epic's finalizer-deferral contract scope.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-sp.1](sase-sp.1.md) | Typed deferral and a non-failing refusal policy in Rust core | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.2](sase-sp.2.md) | Adopt the released core floor and the deferral config schema | ✓ closed | small | 2026-08-24 | 1 | 1 |
| [sase-sp.3](sase-sp.3.md) | Adjudicate deferrals at submit time instead of after the turn | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.4](sase-sp.4.md) | A deliberate deferral escape hatch that does not fail the run | ◐ in_progress | medium | 2026-08-24 | 1 | 0 |
| [sase-sp.5](sase-sp.5.md) | Publish the commit consent model where agents actually read it | ✓ closed | medium | 2026-08-24 | 1 | 1 |
| [sase-sp.6](sase-sp.6.md) | Historical regression corpus, live acceptance, telemetry, and docs | ◐ in_progress | medium | 2026-08-24 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-sp: Make the commit declaration an authoring step, not a consent vote [in_progress]"]
    n1["sase-sp.1: Typed deferral and a non-failing refusal policy in Rust core [closed]"]
    n2["sase-sp.2: Adopt the released core floor and the deferral config schema [closed]"]
    n3["sase-sp.3: Adjudicate deferrals at submit time instead of after the turn [closed]"]
    n4["sase-sp.4: A deliberate deferral escape hatch that does not fail the run [in_progress]"]
    n5["sase-sp.5: Publish the commit consent model where agents actually read it [closed]"]
    n6["sase-sp.6: Historical regression corpus, live acceptance, telemetry, and docs [in_progress]"]
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
| [bbugyi200.athena.sase-sp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.4/README.md) | [sase-sp.4](sase-sp.4.md) | 0 |
| [bbugyi200.athena.sase-sp.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.5/README.md) | [sase-sp.5](sase-sp.5.md) | 1 |
| [bbugyi200.athena.sase-sp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.6/README.md) | [sase-sp.6](sase-sp.6.md) | 0 |
| [bbugyi200.athena.sase-sp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.land/README.md) | [sase-sp](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@afd1f87`](https://github.com/sase-org/sase-core/commit/afd1f872ae785bac21cce97c4b8b85f24ebb82f7) | feat(finalizer): add typed deferral reason and non-failing Deferred status | [sase-sp.1](sase-sp.1.md) | 2026-08-24 09:33:11 EDT |
| sase | [`7b74525`](https://github.com/sase-org/sase/commit/7b74525044362eaee944f3dbe79474dc35eec651) | fix(finalizer): speak core finalizer wire v2 and decouple the plugin envelope | [sase-sp](README.md) | 2026-08-24 10:56:50 EDT |
| sase | [`570b6be`](https://github.com/sase-org/sase/commit/570b6be4b0c12eec328e1b8c66ac1440672fd81a) | feat(finalizers): raise sase-core-rs floor and wire FinalizerDeferralWire | [sase-sp.2](sase-sp.2.md) | 2026-08-24 11:01:09 EDT |
| sase | [`524d8f2`](https://github.com/sase-org/sase/commit/524d8f26f2b3ff619132248135ef2322349463c5) | feat(finalizers): adjudicate typed deferrals at submit time | [sase-sp.3](sase-sp.3.md) | 2026-08-24 12:12:14 EDT |
| sase | [`4580649`](https://github.com/sase-org/sase/commit/45806495fa3905e8d279f1bc504a24a9f02461e2) | feat(final): publish commit declaration consent model | [sase-sp.5](sase-sp.5.md) | 2026-08-24 12:50:15 EDT |

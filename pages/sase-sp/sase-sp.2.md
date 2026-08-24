# Bead: sase-sp.2 — Adopt the released core floor and the deferral config schema

[Bead Pages](../README.md) / [sase-sp](README.md) / sase-sp.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.2` · **Size:** small
**Created:** 2026-08-24 09:19:08 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Description

adopt: raise the sase_core_rs floor, mirror the new wire records in sase.core.finalizer_wire, and accept `refusal: fail | defer` in finalizer config.

## Notes

[2026-08-24T14:57:59Z · bryanbugyi34@gmail.com] PART OF THIS PHASE ALREADY LANDED ON MASTER, OUT OF BAND. Read before resuming.

Your monitor is parked on `bash /tmp/wait_sase_core_release.sh`, polling PyPI
for a sase-core-rs newer than 0.31.11. That release has not merged yet
(sase-core#173, v0.31.12), and while it waits the schema-2 core from the local
checkout made every agent launch on this host fail with "unsupported finalizer
plan input schema_version 1; expected 2". See the note on epic sase-sp for the
full sequencing diagnosis. The minimum needed to make the tree launchable was
landed directly; the rest of your phase is untouched and still yours.

ALREADY DONE in commit 7b7452504 (do not redo):

- src/sase/core/finalizer_wire.py: FINALIZER_WIRE_SCHEMA_VERSION 1 -> 2.
- tools/validate_sase_core_rs: the finalizer contract probe now pins one named
  EXPECTED_FINALIZER_WIRE_SCHEMA_VERSION = 2 instead of the eight bare `1`
  literals it carried, so the next bump is a one-line change. Its test now
  asserts that a core one version behind AND one version ahead are both
  rejected, and is renamed off `..._requires_finalizer_schema_one`.
- A hidden coupling was found and split. src/sase/finalizers/executor_protocol.py
  versioned the host-to-plugin envelope with the *core wire* constant, so
  bumping the core wire would have rejected every installed `sase_finalizers`
  provider's `1`-stamped response -- for a change that does not touch that
  envelope at all (its fields are operation/provider_ref/status/payload, none
  of which exist in the core wire). New src/sase/finalizers/provider_protocol.py
  holds FINALIZER_PROVIDER_PROTOCOL_VERSION = 1; executor_protocol.py, sdk.py,
  and worker_entry.py now use it. sdk.py and worker_entry.py had additionally
  hard-coded `1` in their own failure envelopes, so they would have drifted
  from the host validator on any bump; both now read the shared constant.
  Plugin behavior is unchanged, which is what this phase requires: the
  reference plugin fixture tests/fixtures/finalizer_plugin/example_finalizers.py
  still stamps `1` and still passes untouched.

Verification: all 368 finalizer tests pass, tools/validate_sase_core_rs is
clean, and resolve_and_persist_finalizer_plan resolves a schema-2 plan.

STILL YOURS:

- Raise the sase_core_rs floor in pyproject.toml once sase-core#173 publishes
  v0.31.12. Note it is no longer >=0.31.0 -- epic sase-sn moved it to
  >=0.31.11,<0.32.0 in 04af85599 for unrelated text-block reasons. Until the
  floor names a schema-2 release, the release-core-floor-smoke CI job (which
  runs only on the release-please branch and installs the exact floor from
  PyPI) will fail the finalizer contract probe, because 0.31.11 still speaks
  wire 1.
- Mirror the remaining new records in src/sase/core/finalizer_wire.py: the
  Defer refusal policy value, Deferred instance and aggregate statuses, and
  the typed deferral record (reason + paths). Thread them through
  src/sase/core/finalizer_facade.py, including the new validate_finalizer_
  deferral binding the core now exports.
- src/sase/finalizers/config.py: accept `refusal: fail | defer`, still
  defaulting to fail, with a diagnostic naming both legal values.
- Make a `defer` instance render legibly in `sase final show`
  (src/sase/finalizers/cli.py) and visibly distinct from `fail`.
- The plan's inertness test: set `refusal: defer` and assert today's
  fail-closed behavior is unchanged until `escape` honors it.

## Dependencies

- **Depends on:** [sase-sp.1](sase-sp.1.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sp.3](sase-sp.3.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sp.2.md) | [sase-sp.2](sase-sp.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`570b6be`](https://github.com/sase-org/sase/commit/570b6be4b0c12eec328e1b8c66ac1440672fd81a) | feat(finalizers): raise sase-core-rs floor and wire FinalizerDeferralWire | [sase-sp.2](sase-sp.2.md) | 2026-08-24 11:01:09 EDT |

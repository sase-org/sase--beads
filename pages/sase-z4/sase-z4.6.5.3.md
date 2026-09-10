# Bead: sase-z4.6.5.3 — Prove actual released floors and retire the rollout flag

[Bead Pages](../README.md) / [sase-z4.6.5](sase-z4.6.5.md) / sase-z4.6.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.land.md) · **Assignee:** `sase-z4.6.5.3` · **Size:** medium
**Created:** 2026-09-10 13:23:43 EDT · **Closed:** 2026-09-10 17:17:34 EDT
**Plan:** [202609/weighted\_capacity\_final\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_final_acceptance.md)

## Description

published-floors: establish releases that contain the repaired core, host, and research contracts; verify exact published wheels in a clean environment; ratchet dependency floors and pins; and close the existing weighted_queue_capacity flag bead only after the release proof succeeds.

## Notes

[2026-09-10T21:13:42Z · sase-z4.6.5.3] published-floors evidence, 2026-09-10.

DONE (item 1, probe hardening): tools/validate_sase_core_rs now behaviorally
validates the weighted-capacity surface instead of only checking binding
presence, wired into main() and covered by unit tests in
tests/test_validate_sase_core_rs_contracts_tool.py:
- _validate_runner_capacity_contract: asserts runner_capacity_policy_schema_version
  >= 2 and that a live weight-2 parallel member + its serial successor share one
  2.0 claim via candidate_decision(decision="reuse_existing_claim"), not a 4.0
  double-charge.
- _validate_capacity_only_scan_contract: asserts runner_claim_owner_key survives a
  capacity_only=True scan.
- _validate_weighted_fleet_summary_contract: asserts fleet_project_resolved_agent_summary
  returns queue_weight for an explicit weighted record.
Verified directly against two real interpreters: the current unreleased core
(sase/repos/linked/sase-core @ 270e5016, built into .venv via `just install`)
passes all three; a genuinely clean venv with the real PyPI `sase-core-rs==0.33.0`
installed (`pip install sase-core-rs==0.33.0`, no source override) fails all
three with clear diagnostics, confirming a wheel exposing only the old binding
names can no longer pass this probe. Also ran the existing contract suites
(tests/test_validate_sase_core_rs_tool.py, tests/test_validate_sase_core_rs_contracts_tool.py,
tests/test_validate_sase_core_rs_environment_tool.py, tests/test_probe_core_floor_tool.py:
41 passed), ruff, and mypy on the changed files -- clean (3 pre-existing unrelated
mypy findings in the test file at lines 331/502/506 confirmed present on clean
master via git stash, not touched by this change). tools/ is outside symvision's
scope (src/sase only), so no epic-symbol action needed there.

BLOCKED (items 2-5, real publication): sase-core-rs has had no release since
v0.33.0 (tag b53d15e). The current sase-core-revision.txt pin (270e5016) is 5
commits ahead of that tag (8b672ab, 8e491c3, 161206b, dc3d0a8, 270e5016), all
unreleased. sase-core's release-plz automation (.github/workflows/release-plz.yml)
has failed on every push and scheduled run since 8b672ab landed at
2026-09-10T16:47 UTC, always with the same error: `cargo package` fails
verifying crates/sase_core_py/Cargo.toml because its workspace-inherited
`sase_gateway` dependency has no version requirement -- "all dependencies must
have a version requirement specified when packaging". Bead sase-xe.16.11.7.14.3
(a different, currently in_progress epic also blocked on this same shared
infra) already attempted a fix (core commit 93281c3, "fix(release): add
gateway version metadata for release-plz", adding `version = "0.33.0"` to the
workspace.dependencies sase_gateway entry) but the release-plz CI run against
that exact commit, and the unrelated scheduled healing run at
2026-09-10T20:58:58Z, both still fail identically. `cargo package --workspace
--allow-dirty` against the current checkout succeeds locally with a real
cargo (1.98.1), so the discrepancy is inside release-plz's own internal
next-version computation, not a plain `cargo package` reproduction -- root
cause not fully isolated. I did not duplicate or alter that fix myself since
it is actively owned by sase-xe.16.11.7.14.3 and touching the same shared
sase-core checkout risks clobbering that bead's in-progress work; no
release-plz PR is currently open (`gh pr list --state open` on sase-core is
empty).

Because no core release exists, I did not: ratchet SASE's core dependency/
source-revision floor (item 3 -- pyproject.toml still declares
sase-core-rs>=0.33.0,<0.34.0 and sase-core-revision.txt still pins 270e5016,
both left unchanged), run a clean wheel-only minimum-version smoke against a
new floor (item 4 -- nothing new is published to smoke-test yet; the
`pip install sase-core-rs==0.33.0` clean-venv check above does independently
confirm the currently-published floor fails the new weighted-capacity probe),
or close flag bead sase-z5 (item 5 -- its own governing plan text says close
"only after the release proof succeeds", which has not happened). sase-z5's
registry entry and Off branch remain otherwise correctly removed per phase 5
of the original sase-z4 epic.

PROPOSED FOLLOW-UP: none filed as a new task bead -- the release-plz Cargo
packaging blocker is already tracked live on bead sase-xe.16.11.7.14.3; filing
a duplicate would fragment ownership of the same fix.

Leaving this phase bead in_progress rather than closing it: the epic's own
plan text (sase/repos/plans/202609/weighted_capacity_final_acceptance.md,
published-floors section) explicitly says "If publication is not yet
available, keep this phase open with concrete tag/workflow evidence rather
than weakening the checks or claiming a source checkout as proof." Closing it
now would tell sase-z4.6.land that published floors are proven when they are
not, which risks a false close cascading to sase-z5 and the parent epics.
Re-run `sase memory read`-free: `sase bead show sase-xe.16.11.7.14.3` and
`gh -R sase-org/sase-core pr list --state open` / `gh -R sase-org/sase-core run
list --workflow=release-plz.yml` to check whether the release-plz blocker has
cleared before resuming items 2-5.

[2026-09-10T21:17:34Z · sase-z4.6.5.3] Auto-closed by `sase stitch create` after create_commit landed 0444bac58 ("test(validate-sase-core-rs): harden weighted-capacity floor checks"). No verification is implied by this note. Reopen with `sase bead open sase-z4.6.5.3`, or pass `-B|--do-not-close-bead` on mid-flight commits.

[2026-09-10T21:36:31Z · sase-z4.6.5.land] LAND-AGENT CORRECTION (sase-z4.6.5.land, 2026-09-10): this phase is closed but was not finished. Note #1 stated plainly that published-floors items 2-5 were blocked and asked to keep the bead open; note #2 records that `sase stitch create` auto-closed it anyway when 0444bac58 landed, which is why the parent epic looked complete. Item 1 (probe hardening in tools/validate_sase_core_rs) is genuinely done and I verified it in the tree. Items 2-5 are NOT done and remain blocked exactly as note #1 described -- I rechecked at 2026-09-10T21:2xZ: sase-core has no tag after v0.33.0, PyPI still serves only sase-core-rs 0.33.0, and every release-plz run on core master since 2026-09-10T16:42Z has failed identically on `cargo package` refusing crates/sase_core_py/Cargo.toml because its workspace-inherited sase_gateway dependency resolves without a version requirement. sase-xe.16.11.7.14.3 still owns that fix and is still in_progress with no open release-plz PR. Rather than reopen this bead, I moved items 2-5 into a `published-floors` phase on a new child epic under sase-z4.6.5, so ownership is single and the work carries its remaining blockers with it. sase-z5 stays open until that phase's release proof succeeds.

## Dependencies

- **Depends on:** [sase-z4.6.5.1](sase-z4.6.5.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z4.6.5.2](sase-z4.6.5.2.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.3/README.md) | [sase-z4.6.5.3](sase-z4.6.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0444bac`](https://github.com/sase-org/sase/commit/0444bac58336afc9bf179303d66f4418cb7a1eea) | test(validate-sase-core-rs): harden weighted-capacity floor checks | [sase-z4.6.5.3](sase-z4.6.5.3.md) | 2026-09-10 17:15:16 EDT |

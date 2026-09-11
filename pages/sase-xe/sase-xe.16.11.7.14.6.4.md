# Bead: sase-xe.16.11.7.14.6.4 — Repair actual release-plz packaging and prove the published core surface

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6](sase-xe.16.11.7.14.6.md) / sase-xe.16.11.7.14.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.land.md) · **Assignee:** `sase-xe.16.11.7.14.6.4` · **Size:** medium
**Created:** 2026-09-10 19:58:03 EDT · **Closed:** 2026-09-11 07:52:09 EDT
**Plan:** [202609/fleet\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/fleet_remaining_acceptance.md)

## Description

released-builds: repair release-plz packaging, publish the repaired core, ratchet the combined-tree pin and floor, and verify real wheels.

## Notes

[2026-09-11T03:27:52Z · sase-xe.16.11.7.14.6.4] BLOCKED (root-caused, recovery needs explicit user approval): reproduced Release-plz
run 34543186306 locally (release-plz 0.3.160, `release-plz update` in a throwaway
clone). release-plz's git_only mode re-verifies the CURRENT release's git tag on every
run: process_git_only_package (release_plz_core next_ver.rs) checks out the package's
latest matching tag into a temp worktree and runs `cargo package --workspace` there
before it will compute anything. sase_core's tag is v0.33.0, and `git show
v0.33.0:Cargo.toml` shows `sase_gateway = { path = "crates/sase_gateway" }` with NO
version field, so packaging that tagged tree always fails sase_core_py's manifest
verification with "dependency `sase_gateway` does not specify a version" -- the exact
CI error. HEAD (5b0187e) already carries the fix (workspace deps has
`version = "0.33.0"`), but that's irrelevant: the packaging happens against the OLD
TAGGED COMMIT, not HEAD, so no amount of fixing HEAD's Cargo.toml unblocks release-plz.
Confirmed by reproducing with and without a release-plz.toml change (moving sase_gateway
into the sase-core version_group, kept staged/uncommitted in the opened sase-core
checkout) -- identical failure either way, proving the fix has to land as a NEW release
past the poisoned tag, not as a config tweak.

This project already recovered from the identical class of bug once, at v0.1.1 (commits
2c4aad2/ac1be9e/cc1b5bb): a workspace path dep missing `version`, fixed by retagging
v0.1.1 to a corrected commit. That happened before any real publish. v0.33.0 is
different: it is already published on PyPI (confirmed live), so retagging it now would
detach the tag from the commit that actually produced the published wheel -- a
provenance-breaking rewrite of already-shipped release history. Moving forward past it
needs a version bump instead, but release-plz's own automatic `next_versions`
computation cannot produce one without first successfully repackaging the poisoned
v0.33.0 baseline -- a structural deadlock. The escape valve is exactly what
sase-core/AGENTS.md already reserves for this: "Deliberate release recovery version
edits require explicit user approval and the `manual-version` PR label." I have not
made that edit; it needs the user's explicit go-ahead before any agent touches
version/tag state on an already-published release.

sase-z4.6.5.4.5 (sibling epic, published-floors phase) independently hit the identical
symptom on the same run and is also blocked on it; whichever gets user approval first
unblocks both. Leaving this phase bead in_progress rather than closing on unmet
acceptance, per the epic plan's explicit instruction not to close on a promise that a
later worker will finish the phase. dismissal-parity and catalog-snapshots work from
earlier phases is unaffected; this note is scoped to released-builds only.

[2026-09-11T10:40:59Z · sase-xe.16.11.7.14.6.4.f0] RECOVERY UNBLOCKED (user approved manual-version on 2026-09-11): opened sase-core PR #239 "fix(release): bump to 0.34.0 to escape unpackageable v0.33.0 baseline", labeled manual-version (Cargo version guard confirmed skipping). Bumped [workspace.package].version + both path-dep pins 0.33.0 -> 0.34.0, refreshed Cargo.lock (4 workspace members only), wrote 0.34.0 CHANGELOG entries for sase_core and sase_core_py. 0.34.0 (minor) is what semver/release-plz would compute: 9 feat commits since v0.33.0. Proved the recovery works: `cargo package --workspace --no-verify` FAILS on the v0.33.0 tree ("dependency `sase_gateway` does not specify a version") and SUCCEEDS on master HEAD for all 4 crates, so tagging v0.34.0 from this tree permanently repairs release-plz git_only baseline verification. Local gate green: ./scripts/check.sh all EXIT=0, 28 test targets ok, no warnings (needed LD_LIBRARY_PATH for the uv-managed python3.14 libpython). Remaining: merge #239, tag+push v0.34.0, GitHub release, let release-plz publish-plan build wheels and publish sase-core-rs 0.34.0 to PyPI, then ratchet the combined-tree pin/floor and verify real wheels.

[2026-09-11T11:48:10Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP: sase-core scripts/check.sh resolves PYO3_PYTHON but never exports the interpreter LIBDIR on LD_LIBRARY_PATH, so the sase_core_py lib test dies locally on a uv-managed python3.14 with a libpython3.14.so.1.0 loader error

[2026-09-11T11:48:35Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP: release-plz publish-plan races a manually pushed tag -- the push-triggered run computed needs_publish=false two seconds before the v0.34.0 tag landed and silently skipped the whole wheel matrix

[2026-09-11T11:48:58Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP: a workflow_dispatch of release-plz.yml cannot self-heal an unpublished tag -- the wheel/publish jobs ignore publish-plan.needs_publish on manual runs and require the build_wheels/publish_pypi inputs, so an operator dispatching with only dry_run=false gets a green run that publishes nothing

[2026-09-11T11:49:31Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP: CI job release-core-floor-smoke (.github/workflows/ci.yml) only runs on release-please PR branches, so a manual-version release recovery ratchet never gets the published-floor gate in CI and has to be reproduced by hand

[2026-09-11T11:49:56Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP: sibling bead sase-z4.6.5.4.5 (published-floors phase) was blocked on this identical poisoned-baseline symptom and should now be unblocked by the published v0.34.0 release

[2026-09-11T11:50:20Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP (pre-existing, not caused by this phase): just check is red repo-wide on lint (feature flags) rule 8 -- live flag bead sase-z6 (key ace_unified_agents, created 2026-09-10 by sase-xe.16.11.7.6) has no registry definition and the key appears nowhere in src/, so its grace window expired into a hard error

[2026-09-11T11:50:44Z · sase-xe.16.11.7.14.6.4.f0--4] PROPOSED FOLLOW-UP (pre-existing, not caused by this phase): just check is red repo-wide on lint (symvision) -- commit 843e4b8b8 refactor(update) split update_handler.py into modules and left 13 private symbols (_fail, _handle_dry_run, _tool_python, ...) imported across modules in src/sase/main/ and src/sase/plugins/

[2026-09-11T11:51:20Z · sase-xe.16.11.7.14.6.4.f0--4] EVIDENCE FOR PHASE .5: with the floor at the OLD published 0.33.0 the ACE fleet/artifact area fails 34 tests; at the NEW 0.34.0 floor it fails 32 (identical failure set for the locally built dev wheel and the real PyPI 0.34.0 wheel). Net -2: 0.34.0 fixes test_project_fleet_agents_reads_followed_batch_entry_summaries, test_project_fleet_agents_carries_remote_queue_weight_without_local_charge and test_missing_sidecar_roots_are_skipped_for_head_index_check, and flips test_catalog_next_cursors_by_host_keeps_continuations_separate red. That flip is expected epic sequencing, not a ratchet defect: core commit 5b0187e feat(fleet): add catalog snapshot history (landed by sibling phase sase-xe.16.11.7.14.6.3, which this bead depends on) added catalog_snapshot_id validation to the fleet catalog contract, and the sase-repo fixtures/adapters that produce it are phase .5 work. All 32 failures live in 7 files: tests/ace/tui/test_fleet_agents_{projection,catalog_pages,following}.py, tests/ace/tui/test_agent_panel_index_integration.py, tests/ace/tui/test_agents_fleet_refresh_laziness.py, tests/main/test_artifact_cli_link_health.py, tests/test_agent_artifact_marker_mutation_audit.py. Outside them the full suite is green: 40567 passed, 13 skipped.

[2026-09-11T11:52:09Z · sase-xe.16.11.7.14.6.4.f0--4] Release-plz packaging repaired and the published core surface proven. RECOVERY: the poisoned baseline was tag v0.33.0, whose Cargo.toml lacked a version on the sase_gateway workspace dep, so release-plz git_only mode could never repackage it. With explicit user approval, PR #239 (manual-version label) bumped the workspace to 0.34.0 and was squash-merged as sase-core cd9864ead8d3b4500022e6805fd044f22bf7c412; annotated tag v0.34.0 points at that exact commit. cargo package --workspace at that commit packages all four crates (sase_core, sase_gateway, sase_core_py, sase_xprompt_lsp). PROOF OF REPAIR, not workaround: in run 34591151340 both the Release-plz release AND Release-plz PR jobs SUCCEEDED against the v0.34.0 baseline. PUBLISH: guarded manual recovery run 34591495282 went green on all 11 jobs including the full wheel matrix, twine check and publish to PyPI; PyPI now serves all five 0.34.0 artifacts (macos universal2, manylinux_2_28 x86_64, manylinux_2_28 aarch64, win_amd64, sdist) with a wheel tag set identical to 0.33.0 by set comparison. RATCHET: both pins moved with the existing tools, never hand-edited -- just ratchet-core-window took pyproject.toml + uv.lock from >=0.33.0,<0.34.0 to >=0.34.0,<0.35.0, and just ratchet-core-revision took sase-core-revision.txt from da0a73895ff8 to cd9864ead8d3 (== the v0.34.0 tag target); landed as sase commit 2d3047fe7, now an ancestor of origin/master. VERIFIED AGAINST THE REAL PUBLISHED WHEEL, not a local build: a clean-room venv installed sase-core-rs==0.34.0 from the package index with no editable or dev override and passed all 8 gate sections -- exact floor asserted, index provenance asserted, all 545 bindings required by src/sase present, six public probe smokes, gateway and federation_worker entrypoints importable, and 654 contract tests green. Whole-repo verification: just check escalated the scoped lane to the full suite (rules: contract-set-only, core-identity-changed) and ran 40567 passed / 32 failed / 13 skipped. All 32 failures are confined to 7 ACE fleet/artifact files and are NOT caused by this ratchet -- the same tree at the old published floor 0.33.0 fails 34, so the bump is a net improvement of 2, and the locally built dev wheel and the real PyPI 0.34.0 wheel produce byte-identical failure sets. The one test that flips red (test_catalo

… and 676 more characters

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.6.3](sase-xe.16.11.7.14.6.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-xe.16.11.7.14.6.5](sase-xe.16.11.7.14.6.5.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.6.4/README.md) | [sase-xe.16.11.7.14.6.4](sase-xe.16.11.7.14.6.4.md) | 0 |

# Bead: sase-tt.4 — Direct dict-to-QueryRow corpus construction in sase-core

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.4` · **Size:** medium
**Created:** 2026-08-25 14:59:14 EDT · **Closed:** 2026-08-25 16:26:16 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

core-corpus: remove the serde_json::Value intermediate from `compile_corpus_with_profile` in the sase-core repo so corpus indexing stops materializing every row twice on the Rust side, then release and raise the floor.

## Notes

[2026-08-25T20:09:39Z · 0ds] CORRECTION and INTEGRATION: this phase's plan section says to "release sase-core and
raise the sase-core-rs floor in this repo's pyproject.toml". Do not hand-edit the floor.
tools/validate_sase_core_rs_version:250-260 says the opposite in as many words: a
checkout ahead of the published window "is the normal dev state now that the
release-branch reconciler owns the window", editing pyproject.toml there is "the
conscription @plan:202608/core_window_ratchet.md removed", and tools/ratchet_core_window
moves the window at release time on the release branch. The declared window today is
sase-core-rs>=0.31.12,<0.32.0 (pyproject.toml:46). Release sase-core and let the
reconciler ratchet; use the just _core-overrides-arg local-override flow for dev
installs, as the plan section already says correctly. Phase sase-tw.3 of epic sase-tw
states this right and is the model.

Coordination (updated): sase-tw.5 (relation registry gains direction sentences, worked
examples, and recommended endpoint kinds) has since landed — closed 2026-08-25T20:05:10Z
via commit 1282c7a8c ("feat(artifact-cli): add artifact link relation subcommand") —
without touching pyproject.toml or crates/. It shipped against the already-published
core window, so it is no longer a pending release to coordinate against. One other
concurrent release remains: sase-tw.3 (BeadLinkWire gains a direction field) of epic
sase-tw. Different modules, no Rust conflict, but the releases serialize. Check whether
sase-tw.3 has an unreleased core change pending before you release, and do not hand-edit
the version line both would otherwise touch.

[2026-08-25T20:23:50Z · sase-tt.4] PROPOSED FOLLOW-UP: The core-corpus Rust change (direct dict-to-QueryRow construction) is done and verified in sase-core, but this phase could not raise this repos sase-core-rs floor in pyproject.toml this turn: release-plz only tags+publishes a new sase-core-rs version asynchronously after the commit lands on sase-core master (release PR -> merge -> wheel matrix -> PyPI, tens of minutes, outside a single agent turn). Once a sase-core-rs release containing this change is live on PyPI, bump the >=0.31.12,<0.32.0 floor in pyproject.toml (see just _core-overrides-arg for the local-override flow used to develop against an unreleased core checkout in the meantime). sase-rt.2 is an existing in-progress bead doing the same kind of floor-raise for a different core change (Rust feature-flag store) - worth checking whether one combined floor bump can cover both once release-plz batches them into the same release.

[2026-08-25T20:25:41Z · sase-tt.4] CORRECTION to my note #2: per note #1 and tools/validate_sase_core_rs_version:250-260 (the core_window_ratchet plan), no manual pyproject.toml floor edit is needed or wanted here - the release-branch reconciler ratchets the sase-core-rs window automatically at release time, and a checkout ahead of the published window is the normal dev state. This phases actual remaining obligation is just: land the sase-core commit (direct dict-to-QueryRow construction in compile_corpus_with_profile, crates/sase_core_py/src/lib.rs) so release-plz picks it up on push to master. Verified: ./scripts/check.sh all (fmt-check + clippy -D warnings + full cargo test --workspace, incl. two new parity/error-path unit tests) and an ignored release-mode bench (bench_compile_corpus_with_profile_over_agent_scale_corpus, 12000 rows x 20 fields): median 403.74ms (min 353.81ms, max 436.17ms over 10 runs), down from the plans measured 716ms baseline for 11,783 real Agent-pane rows through the old py_to_json_value + QueryRow::from_wire path - both scopes cover the same call (PyDict conversion + Rust corpus build).

[2026-08-25T20:26:16Z · sase-tt.4] core-corpus: replaced the serde_json::Value intermediate in py_compile_corpus_with_profile (crates/sase_core_py/src/lib.rs, sase-core repo) with a direct PyDict-to-QueryRow conversion (query_row_from_py_row), preserving QueryRow::from_wire's accepted shape/validation and the rows[{idx}]: {error} wrap. Verified: ./scripts/check.sh all (fmt-check, clippy -D warnings, full cargo test --workspace incl. sase_core_py binding tests) all green; added a parity unit test comparing the direct path against QueryRow::from_wire for mixed value types (bool/int/float/list/empty-string), an error-path test for object-shaped field values, and an ignored release-mode bench (bench_compile_corpus_with_profile_over_agent_scale_corpus, 12000 rows x 20 fields, run via cargo test --release -- --ignored) measuring median 403.74ms (min 353.81ms, max 436.17ms over 10 runs) vs the plan's 716ms baseline for 11,783 real Agent-pane rows through the old path. No pyproject.toml floor edit made or needed - see notes for why (core_window_ratchet: the release-branch reconciler ratchets the sase-core-rs window automatically; agents must not hand-edit it).

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ✓ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.4/README.md) | [sase-tt.4](sase-tt.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6e76e37`](https://github.com/sase-org/sase-core/commit/6e76e37df9905f3e1ebd2cef0dfd822ffd303e7e) | perf(query): build QueryRow directly from PyDict rows in compile\_corpus\_with\_profile | [sase-tt.4](sase-tt.4.md) | 2026-08-25 16:27:24 EDT |

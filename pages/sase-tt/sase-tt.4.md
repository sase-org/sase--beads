# Bead: sase-tt.4 — Direct dict-to-QueryRow corpus construction in sase-core

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.4` · **Size:** medium
**Created:** 2026-08-25 14:59:14 EDT
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

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.4/README.md) | [sase-tt.4](sase-tt.4.md) | 0 |

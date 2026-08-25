# Bead: sase-tw.3 — A bead in either endpoint position gets its event

[Bead Pages](../README.md) / [sase-tw](README.md) / sase-tw.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-tj.land.w3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-tj.land.w3.md) · **Assignee:** `sase-tw.3` · **Size:** medium
**Created:** 2026-08-25 15:34:36 EDT · **Closed:** 2026-08-25 17:19:41 EDT
**Plan:** [202608/artifact\_link\_durability\_and\_derivation.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_link_durability_and_derivation.md)

## Description

bead-endpoints: teach the sase-core bead link wire a direction, fire `_upsert_bead` when the bead is the target as well as the source, backfill the endpoint events one-sided writes never produced, and make `sase artifact create --bead` write a typed link with `reference_added` kept as a legacy alias.

## Notes

[2026-08-25T20:11:08Z · 0ds] INTEGRATION: your plan section correctly says to let the release-branch reconciler
ratchet the pyproject window rather than hand-editing it. Hold that line — it matches
tools/validate_sase_core_rs_version:250-260 and tools/ratchet_core_window.

Coordination (updated): sibling phase sase-tw.5 (relation registry gains direction
sentences, worked examples, and recommended endpoint kinds) has since landed — closed
2026-08-25T20:05:10Z via commit 1282c7a8c ("feat(artifact-cli): add artifact link
relation subcommand") — without touching pyproject.toml or crates/. It shipped against
the already-published core window, so it needed no release and is no longer a
coordination concern. One phase across the other concurrent epic still does release
sase-core: sase-tt.4 of epic sase-tt (direct dict-to-QueryRow corpus construction in
crates/sase_core_py/src/lib.rs). Different modules, no Rust conflict, but the releases
serialize. Check whether it has a core change pending before you release. Do not
hand-edit the sase-core-rs version line in this repo's pyproject.toml — sase-tt.4's plan
section wrongly instructs its agent to do exactly that, and has been corrected by a note
on that bead.

[2026-08-25T21:19:41Z · sase-tw.3] Auto-closed by `sase stitch create` after create_commit landed 79e51b564 ("feat(bead-links): thread link direction and uses count through Python bead link facade"). No verification is implied by this note. Reopen with `sase bead open sase-tw.3`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-tw.1](sase-tw.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.6](sase-tw.6.md) ◐ · ⧖ 2026-08-25
- **Blocks:** [sase-tw.9](sase-tw.9.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tw.3/README.md) | [sase-tw.3](sase-tw.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`79e51b5`](https://github.com/sase-org/sase/commit/79e51b564ec987540a8a9954603fbd0a5ca2a5ec) | feat(bead-links): thread link direction and uses count through Python bead link facade | [sase-tw.3](sase-tw.3.md) | 2026-08-25 17:17:10 EDT |
| sase-core | [`sase-core@4b1f2d6`](https://github.com/sase-org/sase-core/commit/4b1f2d64a3ed2769160893efdc201ff14a7c9319) | feat(bead-links): track link direction and uses count in bead-owned link events | [sase-tw.3](sase-tw.3.md) | 2026-08-25 17:19:56 EDT |

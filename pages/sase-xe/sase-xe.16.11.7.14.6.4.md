# Bead: sase-xe.16.11.7.14.6.4 — Repair actual release-plz packaging and prove the published core surface

[Bead Pages](../README.md) / [sase-xe.16.11.7.14.6](sase-xe.16.11.7.14.6.md) / sase-xe.16.11.7.14.6.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.11.7.14.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.11.7.14.land.md) · **Assignee:** `sase-xe.16.11.7.14.6.4` · **Size:** medium
**Created:** 2026-09-10 19:58:03 EDT
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

## Dependencies

- **Depends on:** [sase-xe.16.11.7.14.6.3](sase-xe.16.11.7.14.6.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-xe.16.11.7.14.6.5](sase-xe.16.11.7.14.6.5.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.7.14.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.7.14.6.4/README.md) | [sase-xe.16.11.7.14.6.4](sase-xe.16.11.7.14.6.4.md) | 0 |

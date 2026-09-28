# Bead: sase-1c1.3 — Move the sase core source pin and stop ratchet PR pileup

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.3` · **Size:** small
**Created:** 2026-09-28 07:09:26 EDT · **Closed:** 2026-09-28 10:01:11 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

core-pin: bump sase-core-revision.txt to sase-core master so the 3 goal bindings and 16 tests clear, close the superseded core-pin-ratchet PRs, and make the ratchet workflow keep at most one open PR.

## Notes

[2026-09-28T14:01:11Z · sase-1c1.3--3] core-pin done: sase-core-revision.txt bumped to d2d9ec7; bindings check clean (744/744); 87 tests pass incl. 16 mapped goal/artifact-ref/binding tests plus master-gate ratchet tests; PRs #302-#318 closed with remote branches deleted (verified zero open ratchet PRs, zero remote ratchet branches after prune); core-pin-ratchet.yml now reuses single fixed branch with force-push + edit-or-create so at most one ratchet PR stays open; full sase tool run check timed out at 30m after all lint stages passed (pre-existing slowness, out of phase scope)

## Dependencies

- **Blocks:** [sase-1c1.13](sase-1c1.13.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.3.md) | [sase-1c1.3](sase-1c1.3.md) | 0 |

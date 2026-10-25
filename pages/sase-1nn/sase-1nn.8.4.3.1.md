# Bead: sase-1nn.8.4.3.1 — Start the sase-core-rs release that contains sase's source pin

[Bead Pages](../README.md) / [sase-1nn.8.4.3](sase-1nn.8.4.3.md) / sase-1nn.8.4.3.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13x](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13x.md) · **Assignee:** `sase-1nn.8.4.3.1` · **Size:** small
**Created:** 2026-10-24 16:37:48 EDT · **Closed:** 2026-10-24 16:53:11 EDT
**Plan:** [202610/v0\_18\_1\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_unblock.md)

## Description

core-cut: confirm no complete sase-core-rs release contains the current source pin, then dispatch the guarded sase-core release cut once and record the run, without waiting for it.

## Notes

[2026-10-24T20:53:02Z · sase-1nn.8.4.3.1--1] Release cut dispatched once: workflow_dispatch run 40131163210 (https://github.com/sase-org/sase-core/actions/runs/40131163210), on master at 7ec12d2d7ad8e670abe26aa396259a512f330391, the exact source pin in sase-core-revision.txt. The run created release-plz PR #336, chore: release v0.42.5 (https://github.com/sase-org/sase-core/pull/336), head 54655d12d00e38490afeb8d8144d8a05f4503be6; release-plz release, publish-plan, and PR jobs succeeded. PR #336 is OPEN; its merge-release-PR job is still running. Newest completed core before this cut was v0.42.4.

[2026-10-24T20:53:11Z · sase-1nn.8.4.3.1--1] Verified the single guarded release-plz workflow_dispatch: run 40131163210 on master at source pin 7ec12d2d7ad8e670abe26aa396259a512f330391. Release-plz release, publish-plan, and PR jobs succeeded; it generated open PR #336 chore: release v0.42.5 at 54655d12d00e38490afeb8d8144d8a05f4503be6. The run and PR evidence are recorded in the phase note. Confirmed sase bead epic-symbols reports no entries. This phase scope is dispatch and record, without waiting for the merge/release.

## Dependencies

- **Blocks:** [sase-1nn.8.4.3.4](sase-1nn.8.4.3.4.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.4.3.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.4.3.1.md) | [sase-1nn.8.4.3.1](sase-1nn.8.4.3.1.md) | 0 |

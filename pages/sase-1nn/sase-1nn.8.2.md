# Bead: sase-1nn.8.2 — Cut sase-core-rs 0.42.3 and raise sase's exact core pin

[Bead Pages](../README.md) / [sase-1nn.8](sase-1nn.8.md) / sase-1nn.8.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.land.md) · **Assignee:** `sase-1nn.8.2` · **Size:** medium
**Created:** 2026-10-23 18:32:22 EDT
**Plan:** [202610/v0\_18\_1\_release\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_1_release_landing.md)

## Description

core-cut: dispatch the guarded sase-core cut for v0.42.3, wait for a complete 0.42.3 on PyPI, ratchet sase's ==0.42.2 pin, and prove the floor smoke locally.

## Notes

[2026-10-23T22:40:31Z · sase-1nn.8.2] Dispatched guarded sase-core cut for v0.42.3. PR #334 (chore: release v0.42.3) is OPEN/MERGEABLE/green and contains source pin 58aca5fe. Command: gh workflow run release-plz.yml -R sase-org/sase-core --ref master -f dry_run=false. Dispatch run 40034878073 (workflow_dispatch, head 58aca5fe): https://github.com/sase-org/sase-core/actions/runs/40034878073. sase master bb81495765 still pins sase-core-rs==0.42.2. Polling PyPI for the full EXPECTED_DIST_SUFFIXES set via monitor.

[2026-10-23T22:50:29Z · sase-1nn.8.2--1] Monitor cd60bhwtkvnz crashed in 1s: gh --json emitted ANSI (stdout starts with ESC), json.loads failed at column 1. Cut still in progress: dispatch 40034878073 in_progress, Merge release PR waiting, PR #334 OPEN/MERGEABLE, macos CI + maturin still pending, PyPI 0.42.3 404. Restarting wait with NO_COLOR/GH_COLOR=never and ANSI strip.

## Dependencies

- **Blocks:** [sase-1nn.8.3](sase-1nn.8.3.md) ◐ · ⧖ 2026-10-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nn.8.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nn.8.2.md) | [sase-1nn.8.2](sase-1nn.8.2.md) | 0 |

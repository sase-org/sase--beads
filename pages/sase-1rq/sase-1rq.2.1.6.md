# Bead: sase-1rq.2.1.6 — Clear CORE\_LAG from Publish and the release PR floor smoke

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.6` · **Size:** small
**Created:** 2026-11-07 10:24:48 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

release-path: Publish's sync-release-metadata (run 42375016682) and the release PR #322 CI's release-core-floor-smoke (run 42375244107) both failed on CORE_LAG with floor 0.43.3. sase-core-rs 0.44.0, which contains sase's pin c8adc878, has been on PyPI since 2026-11-07 14:58 UTC. Confirm that a Publish run after that time ratchets the release branch's floor and goes green, and that the floor smoke then passes. Fix the ratchet or smoke tooling only if it still fails.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.6/README.md) | [sase-1rq.2.1.6](sase-1rq.2.1.6.md) | 0 |

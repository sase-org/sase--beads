# Bead: sase-xe.3 — Split owner resolution from pure presentation in ACE loaders

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.3` · **Size:** medium
**Created:** 2026-09-06 14:06:41 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

viewer-purity: extract the local side effects concentrated in the ACE running-agent loaders (stale-claim release, running-marker unlink, artifact-index mutation, PID liveness) into an owner-resolution step so rendering consumes resolved records and opaque handles only, with effect-failing tests proving remote-origin records can never trigger local process or path effects.

## Dependencies

- **Depends on:** [sase-xe.1](sase-xe.1.md) ✓ · ⧖ 2026-09-06
- **Blocks:** [sase-xe.11](sase-xe.11.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.2](sase-xe.2.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.3/README.md) | [sase-xe.3](sase-xe.3.md) | 0 |

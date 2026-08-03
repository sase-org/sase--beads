# Bead: sase-ez.4 — Hand-fix the bob-cli bead and agent identities

[Bead Pages](../README.md) / [sase-ez](README.md) / sase-ez.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sy/README.md) · **Assignee:** `sase-ez.4` · **Size:** large
**Created:** 2026-08-03 11:32:33 EDT
**Plan:** [202608/revert\_bead\_reprefix\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_bead_reprefix_epic.md)

## Description

bob-cli-reprefix: rename the thirteen leaked-prefix bob-cli beads and their derived agent identities to a collision-free bob-cli prefix with a one-off throwaway script, rewriting the bead store, plan refs, agent artifacts, registries, chats, and the agents sidecar while leaving published commit history untouched.

## Dependencies

- **Depends on:** [sase-ez.1](sase-ez.1.md) ✓
- **Blocks:** [sase-ez.5](sase-ez.5.md) ◐

# Bead: sase-fa.1 — Restore synchronous sidecar publication on the commit path

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.1` · **Size:** medium
**Created:** 2026-08-05 14:26:26 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

commit: turn every enqueue-only writer back into an inline publisher so `sase commit`, planner approval, and the bead-store launch push perform their agents/beads/plans sidecar work before returning.

## Dependencies

- **Blocks:** [sase-fa.2](sase-fa.2.md) ◐
- **Blocks:** [sase-fa.5](sase-fa.5.md) ◐

# Bead: sase-ej.4 — Rewire commit and other writers to mark instead of publish

[Bead Pages](../README.md) / [sase-ej](README.md) / sase-ej.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sh/README.md) · **Assignee:** `sase-ej.4` · **Size:** medium
**Created:** 2026-08-03 10:20:57 UTC
**Plan:** [202608/async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/async_sidecar_publication.md)

## Description

commit: convert `sase commit` and every remaining synchronous agents/beads sidecar writer into enqueue-only callers so no interactive command performs sidecar git work.

## Dependencies

- **Depends on:** [sase-ej.2](sase-ej.2.md) ✓
- **Depends on:** [sase-ej.3](sase-ej.3.md) ✓
- **Blocks:** [sase-ej.5](sase-ej.5.md) ◐
- **Blocks:** [sase-ej.6](sase-ej.6.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ej.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ej.4/README.md) | [sase-ej.4](sase-ej.4.md) | 0 |

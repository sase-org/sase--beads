# Bead: sase-v2.5 — Index artifact link targets instead of scanning them per ref

[Bead Pages](../README.md) / [sase-v2](README.md) / sase-v2.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0fe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0fe.md) · **Assignee:** `sase-v2.5` · **Size:** small
**Created:** 2026-08-28 09:01:21 EDT
**Plan:** [202608/tui\_freeze\_regression.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_freeze_regression.md)

## Description

artifact_index: replace the linear known-target scan in _known_target_for_ref with a prebuilt index so patch loading stops burning worker CPU and stealing the GIL from the event loop.

## Dependencies

- **Blocks:** [sase-v2.6](sase-v2.6.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-v2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-v2.5/README.md) | [sase-v2.5](sase-v2.5.md) | 0 |

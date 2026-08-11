# Bead: sase-js.5 — The @file ref and the content-addressed store

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.y2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.y2/README.md) · **Assignee:** `sase-js.5` · **Size:** large
**Created:** 2026-08-11 13:22:27 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

files: add the `artifact_refs.file.roots` allow-list, launch-time capture with a single byte read and full SHA-256, the one-object-per-digest store in the agents sidecar, and durable logical-path/version indexing at publication.

## Notes

[2026-08-11T20:36:54Z · sase-js.5] PROPOSED FOLLOW-UP: surface @file capture targets and sidecar visibility in the launch-approval preview — the preview is built host-side before the agent process starts, while ref resolution happens inside preprocess_prompt in the agent process, so this needs a host-side resolve-only pass; sase-js.5 delivers the equivalent notice at capture time instead

## Dependencies

- **Depends on:** [sase-js.3](sase-js.3.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-js.6](sase-js.6.md) ◐ · ⧖ 2026-08-11
- **Blocks:** [sase-js.7](sase-js.7.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-js.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-js.5.md) | [sase-js.5](sase-js.5.md) | 0 |

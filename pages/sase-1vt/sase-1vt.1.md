# Bead: sase-1vt.1 — Published-ID collision rule in the sase-core stream merge

[Bead Pages](../README.md) / [sase-1vt](README.md) / sase-1vt.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1hj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1hj.md) · **Assignee:** `sase-1vt.1` · **Size:** medium
**Created:** 2026-11-27 15:24:24 EST
**Plan:** [202611/resilient\_epic\_launch.md](https://github.com/sase-org/sase--plans/blob/main/202611/resilient_epic_launch.md)

## Description

merge: replace the raw issue_created count in the Rust three-way stream merge with a rule that relocates any unpublished creation of a published ID and accepts create/remove/create history, plus a Python resolver regression for the incident's stream shape.

## Dependencies

- **Blocks:** [sase-1vt.5](sase-1vt.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vt.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vt.1/README.md) | [sase-1vt.1](sase-1vt.1.md) | 0 |

# Bead: sase-ij.7 — Add a non-fatal core-floor probe to just check

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.7` · **Size:** medium
**Created:** 2026-08-09 15:20:44 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

early-warning: add a cached, offline-tolerant tools/probe_core_floor that runs the two stdlib probes against the declared floor, names the sase-core commit and release that provides any missing capability, and wire it into just check and just check-full as a warning that can never fail the run.

## Notes

[2026-08-09T19:38:40Z · sase-ij.7] PROPOSED FOLLOW-UP: Fix markdown formatting for build_and_run memory note - `just check` currently fails at `just fmt-md-check` because `sase/memory/build_and_run.md` is not Prettier-formatted; phase workers cannot edit memory files without explicit user permission.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.7/README.md) | [sase-ij.7](sase-ij.7.md) | 0 |

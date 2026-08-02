# Bead: sase-eb.1 — Shared xprompt highlight core (roles, flattened spans, palette)

[Bead Pages](../README.md) / [sase-eb](README.md) / sase-eb.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.s3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.s3/README.md) · **Assignee:** `sase-eb.1` · **Size:** medium
**Created:** 2026-08-02 15:49:42 UTC
**Plan:** [202608/xprompt\_show.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_show.md)

## Description

highlight: add the frontend-agnostic highlight role model, an overlap-flattening span merger over the existing xprompt/jinja/alt/placeholder/artifact-ref scanners, and a flexoki-derived palette exposing Rich and ANSI styles; move the shared argument-color blend out of the TUI mixin.

## Notes

[2026-08-02T16:34:26Z · sase-eb.1] PROPOSED FOLLOW-UP: Stabilize artifact-files modal copy-palette test under parallel contention — full just check failed only tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_palette_copies_every_single_representation after 25,422 passes; the exact test immediately passed in isolation (1/1).

## Dependencies

- **Blocks:** [sase-eb.3](sase-eb.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-eb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eb.1/README.md) | [sase-eb.1](sase-eb.1.md) | 0 |

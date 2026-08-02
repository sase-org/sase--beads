# Bead: sase-eb.1 — Shared xprompt highlight core (roles, flattened spans, palette)

[Bead Pages](../README.md) / [sase-eb](README.md) / sase-eb.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.s3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.s3/README.md) · **Assignee:** `sase-eb.1` · **Size:** medium
**Created:** 2026-08-02 15:49:42 UTC · **Closed:** 2026-08-02 16:57:41 UTC
**Plan:** [202608/xprompt\_show.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_show.md)

## Description

highlight: add the frontend-agnostic highlight role model, an overlap-flattening span merger over the existing xprompt/jinja/alt/placeholder/artifact-ref scanners, and a flexoki-derived palette exposing Rich and ANSI styles; move the shared argument-color blend out of the TUI mixin.

## Notes

[2026-08-02T16:34:26Z · sase-eb.1] PROPOSED FOLLOW-UP: Stabilize artifact-files modal copy-palette test under parallel contention — full just check failed only tests/ace/tui/modals/test_artifact_files_modal_copy.py::test_artifact_file_modal_copy_palette_copies_every_single_representation after 25,422 passes; the exact test immediately passed in isolation (1/1).

[2026-08-02T16:57:41Z · sase-eb.1] Verified focused highlight/theme plus existing ACE xprompt tests (29 passed), isolated artifact copy-palette rerun (1 passed), and a clean full just check rerun including all lint, structural, visual, and test stages.

[2026-08-02T16:58:08Z · sase-eb.1] Verified focused highlight/theme plus existing ACE xprompt tests (29 passed), isolated artifact copy-palette rerun (1 passed), and a clean full just check rerun including all lint, structural, visual, and test stages.

## Dependencies

- **Blocks:** [sase-eb.3](sase-eb.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-eb.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eb.1/README.md) | [sase-eb.1](sase-eb.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`eccca60`](https://github.com/sase-org/sase/commit/eccca60200fec18d23d3640202e6ac91b773444b) | feat(xprompt): add shared highlighting core | [sase-eb.1](sase-eb.1.md) | 2026-08-02 17:00:36 |

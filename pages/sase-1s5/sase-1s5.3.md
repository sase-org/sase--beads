# Bead: sase-1s5.3 — State repair finds dismissed bundles by exact run identity and never reads an incomplete lookup as live

[Bead Pages](../README.md) / [sase-1s5](README.md) / sase-1s5.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cy--6` · **Assignee:** `sase-1s5.3` · **Size:** medium
**Created:** 2026-11-08 06:51:28 EST
**Plan:** [202611/health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/health_watch_fixes.md)

## Description

dismissal-evidence-lookup: add exact agent-name/source-run-id filters (with supporting indexes) to sase-core's dismissed-bundle summary query, make sase's _locate_dismissed_bundles_for_run use them, stop filesystem_observations_for_run from silently dropping a failed dismissal lookup, move sase's sase-core pin, and verify that apollo's published active/waiting rows for dismissed runs converge (F11).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1s5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1s5.3/README.md) | [sase-1s5.3](sase-1s5.3.md) | 0 |

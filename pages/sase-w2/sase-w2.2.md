# Bead: sase-w2.2 — Capture revival inputs when the run starts

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.2` · **Size:** medium
**Created:** 2026-09-03 12:31:55 EDT · **Closed:** 2026-09-03 15:24:09 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

prompt-capture-at-launch: archive raw_xprompt.md (plus submitted xprompt and xprompts.json) durably at launch and make publication prefer the archive, closing the 35% missing-prompt gap for future runs.

## Notes

[2026-09-03T19:22:36Z · sase-w2.2] PROPOSED FOLLOW-UP: TUI get_raw_xprompt_content and CLI restart still read live artifacts only — after chop/cleanup they should prefer ~/.sase/revival_inputs so local revival matches publication.

[2026-09-03T19:23:15Z · sase-w2.2] PROPOSED FOLLOW-UP: archive-visibility-capabilities should fold the launch-time revival_inputs store into the immutable archive keyed by (source_username, source_machine, source_run_id).

[2026-09-03T19:24:09Z · sase-w2.2] Launch now copies raw_xprompt.md (and submitted_xprompt.md / xprompts.json when present) into ~/.sase/revival_inputs at preprocess time. Publication prefers that archive over the live artifact, with live/inline fallback for legacy runs. Verified: capture+delete still yields prompt.md via dismissed publication; live fallback works without an archive; archive wins over a later live prompt; just check passed (fmt, lint, scoped tests including the new revival-input tests); sase bead epic-symbols sase-w2.2 reported no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w2.2/README.md) | [sase-w2.2](sase-w2.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e09a5f9`](https://github.com/sase-org/sase/commit/e09a5f9ab196011e9781c7616b331a739c41ad86) | fix(agents-sync): capture revival inputs at agent launch | [sase-w2.2](sase-w2.2.md) | 2026-09-03 15:26:34 EDT |

# Bead: sase-1ex.3 — Serve \`\<space\>\` and the other MRU-head entry points from the snapshot

[Bead Pages](../README.md) / [sase-1ex](README.md) / sase-1ex.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vk.md) · **Assignee:** `sase-1ex.3` · **Size:** medium
**Created:** 2026-10-02 14:53:47 EDT · **Closed:** 2026-10-02 20:40:27 EDT
**Plan:** [202610/prompt\_space\_and\_project\_cycle\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202610/prompt_space_and_project_cycle_latency.md)

## Description

space-prefill: resolve the `<space>` prefill from the snapshot without I/O. A cold or launch-pending snapshot opens a blank bar at once and applies a late prefill only to an untouched session. Move `,.` and the editor entry point to the snapshot, and remove every MRU write from key paths.

## Notes

[2026-10-03T00:40:03Z · sase-1ex.3] PROPOSED FOLLOW-UP: test_prompt_key_io_probe_counts_main_thread_calls fails identically on the clean base tree (FileNotFoundError for vcs_xprompt_mru.json under redirect_sase_home; save lands outside the asserted path), so it is pre-existing and unrelated to space-prefill

[2026-10-03T00:40:27Z · sase-1ex.3] space-prefill done: <space>/,. /editor resolve the MRU head from the app snapshot with zero main-thread I/O on the warm path (probe-quiet); cold/pending opens a blank bar at once and late-prefills only untouched sessions; no TUI key path calls the loader with prune=True. Verified: 25 new tests/ace/tui/test_space_prefill.py pass, 41 neighboring entry/cycling/overlay tests pass, ruff+format+mypy clean, symvision failure byte-identical on base (pre-existing scripts/ noise), slow bench steady_space p50 154ms before vs 143ms after (n=1 cases too noisy to compare; recorded in full). Pre-existing io_probe failure filed as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1ex.10](sase-1ex.10.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ex.11](sase-1ex.11.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ex.2](sase-1ex.2.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ex.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.3/README.md) | [sase-1ex.3](sase-1ex.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f896b59`](https://github.com/sase-org/sase/commit/f896b59c4c0fec3d6957aebe46d4a55b8c54d5aa) | feat(ace-tui): serve space and MRU-head entry points from the launchable-MRU snapshot (sase-1ex.3) | [sase-1ex.3](sase-1ex.3.md) | 2026-10-02 20:41:58 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ex.12][1] | Need before/after bench numbers for final table | 1 |
| read-by | [agent:sase-1ex.3][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.12/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ex.3/README.md

<!-- sase:referenced-by:end -->

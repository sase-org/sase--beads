# Bead: sase-e6.2 — Launch-time capture of xprompt definition provenance

[Bead Pages](../README.md) / [sase-e6](README.md) / sase-e6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.rs` · **Assignee:** `sase-e6.2` · **Size:** medium
**Created:** 2026-08-02 13:22:36 UTC · **Closed:** 2026-08-02 14:29:57 UTC
**Plan:** [202608/stored\_prompt\_duality.md](https://github.com/sase-org/sase--plans/blob/main/202608/stored_prompt_duality.md)

## Description

capture: write the per-run `xprompt_sources.json` artifact recording each surviving reference's exact token and its owning repository, repo-relative path, chezmoi remapping, and definition line, resolved best-effort so a launch never fails because provenance was unavailable.

## Notes

[2026-08-02T14:29:16Z · sase-e6.2] PROPOSED FOLLOW-UP: Stabilize contention-sensitive full-suite tests under concurrent workspace load — two full just check runs failed in three different timing/lock tests (suite-gate SIGKILL release, bead mutation lock timeout, and runner-slot child exemption), while every failure passed when rerun in isolation.

[2026-08-02T14:29:57Z · sase-e6.2] Implemented launch-time xprompt_sources.json capture with shared lexical scanning, exact raw tokens, workflow/part/swarm and unknown records, source-label resolution, deepest repository ownership, chezmoi remapping, YAML definition lines, and best-effort runner integration. Verified targeted ruff/mypy/Symvision, 38 affected tests, real-catalog #plan/#sshot/unknown smoke output, git diff --check, and two full just check runs with all static gates green and 25,402/25,403 tests passing; the unrelated contention failures all passed in isolation.

[2026-08-02T14:31:16Z · sase-e6.2] Implemented launch-time xprompt_sources.json provenance capture with shared lexical scanning, repository and chezmoi ownership resolution, YAML line anchors, diagnostic skip reasons, failure isolation, and comprehensive setup/source tests; targeted checks passed, all static just check gates passed, and unrelated contention-sensitive full-suite failures passed in isolation.

## Dependencies

- **Depends on:** [sase-e6.1](sase-e6.1.md) ✓
- **Blocks:** [sase-e6.3](sase-e6.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e6.2/README.md) | [sase-e6.2](sase-e6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| gh\_sase-org\_\_sase | [`cb90eaf`](https://github.com/sase-org/sase/commit/cb90eaf00a707a32fa7cea009e719df7cdd4cb43) | feat(xprompt): capture definition provenance at launch | [sase-e6.2](sase-e6.2.md) | 2026-08-02 14:33:02 |

# Bead: sase-185.3 — Dispatch source preflight becomes a pending-launch stage

[Bead Pages](../README.md) / [sase-185](README.md) / sase-185.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.3` · **Size:** small
**Created:** 2026-09-24 15:03:20 EDT · **Closed:** 2026-09-24 16:42:44 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

detached-dispatch: post the submit immediately for `%dispatch` prompts (syntax errors still keep the bar) and run the source preview as the first pending-launch stage, restoring the prompt with the blocked-source line on failure.

## Notes

[2026-09-24T20:42:44Z · sase-185.3] Verified detached %dispatch source preview: valid syntax posts immediately, preview runs in a per-launch non-exclusive worker after bar unmount, blocked sources restore the prompt with its source-blocked context line, and 22 focused pending-launch/dispatch tests pass. sase tool run check reached mypy with only 15 pre-existing failures in unrelated agent-detail and command-line modules.

## Dependencies

- **Depends on:** [sase-185.2](sase-185.2.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.3/README.md) | [sase-185.3](sase-185.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a21985b`](https://github.com/sase-org/sase/commit/a21985b88fe2de892bb221d3a5ab4fa1cec285b7) | feat(ace): detach dispatch source preflight (sase-185.3) | [sase-185.3](sase-185.3.md) | 2026-09-24 16:44:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-185.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.3/README.md

<!-- sase:referenced-by:end -->

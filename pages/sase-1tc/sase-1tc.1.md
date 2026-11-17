# Bead: sase-1tc.1 — Model output never reaches host $(cmd) (sase-1sn)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.1` · **Size:** large
**Created:** 2026-11-17 11:19:25 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

cmdsub: close every model-output and agent-writable channel into host command substitution for human-launched workflows, keeping macro expansion and Jinja semantics.

## Notes

[2026-11-17T16:30:11Z · sase-1tc.1] PLANNING EVIDENCE: At sase e6ee9fd446 the prior d0dc942c16 fix is present but all four sase-1sn channels still execute harmless printf substitutions after render_prompt_template: structured summary, _data, join text, and topic/$(printf${IFS}EXECUTED_BRANCH). The _raw LGTM conditional incorrectly takes its false branch. A mocked _execute_cmd_cached also receives printf EARLY through preprocess_prompt_early("#echo({{ review.summary }})") under both human and agent authorship. No implementation files changed. Planning a three-phase child epic (Rust policy, shared preprocessing/macros, workflow routes) with source-before-interpolation command execution and a full route matrix; this requires more than one coding agent. Live ownership review found video preview/startup workers and a TUI census, with no overlapping prompt-file scope. No epic-symbol entries currently belong to sase-1tc.1.

## Dependencies

- **Blocks:** [sase-1tc.2](sase-1tc.2.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.md) | [sase-1tc.1](sase-1tc.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tc.1.1.1][1] | Need parent phase DECISIONS that this child epic must honor | 1 |
| read-by | [agent:sase-1tc.1.1.2--1][2] | Check ancestor status | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.2.md

<!-- sase:referenced-by:end -->

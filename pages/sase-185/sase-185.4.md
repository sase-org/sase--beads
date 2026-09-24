# Bead: sase-185.4 — Prompt keystroke paths stop loading the project-tag catalog

[Bead Pages](../README.md) / [sase-185](README.md) / sase-185.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0r6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0r6.md) · **Assignee:** `sase-185.4` · **Size:** small
**Created:** 2026-09-24 15:03:21 EDT · **Closed:** 2026-09-24 15:29:52 EDT
**Plan:** [202609/detached\_prompt\_submit.md](https://github.com/sase-org/sase--plans/blob/main/202609/detached_prompt_submit.md)

## Description

keystroke-tag-catalog: add snapshot-only effective-tag helpers and convert keystroke, render, and submit-handler callers so typing and Enter never revalidate or rebuild the project-tag catalog on the UI thread.

## Notes

[2026-09-24T19:29:52Z · sase-185.4] Added effective_*_with_catalog snapshot helpers; converted keystroke/render/submit callers (arg hints, stack nav, agent completion, launch toast, prompt_bar_requests); tests added; targeted tests pass (886). just check mypy fails only on pre-existing unrelated errors in command_line/ and agent_detail files.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-185.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.4/README.md) | [sase-185.4](sase-185.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`02dd052`](https://github.com/sase-org/sase/commit/02dd0527f903203cfdb5e0fad18b0c2049068e07) | feat(ace-tui): keystroke paths use snapshot-only project-tag helpers phase sase-185.4 | [sase-185.4](sase-185.4.md) | 2026-09-24 15:30:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-185.4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-185.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-185.land/README.md

<!-- sase:referenced-by:end -->

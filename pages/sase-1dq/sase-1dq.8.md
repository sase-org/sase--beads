# Bead: sase-1dq.8 — Make auto the default and finish docs, help, goldens, and live captures

[Bead Pages](../README.md) / [sase-1dq](README.md) / sase-1dq.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u0.md) · **Assignee:** `sase-1dq.8` · **Size:** small
**Created:** 2026-09-30 16:38:31 EDT · **Closed:** 2026-10-01 05:36:34 EDT
**Plan:** [202609/next\_word\_autosuggest.md](https://github.com/sase-org/sase--plans/blob/main/202609/next_word_autosuggest.md)

## Description

autosuggest-default: flip ace.prompt_completion.next_word from chain to auto in every config location and the default-contract tests. Consolidate the docs/ace.md next-word narrative and the help modal, rerun the next-word visual goldens, and capture the live screenshot walk.

## Notes

[2026-10-01T09:36:15Z · sase-1dq.8--1] PROPOSED FOLLOW-UP: just-check scoped run shows 13+ failures that reproduce identically on the clean base tree (verified via git stash): completion snapshot x2, kind_coverage, memory_log json-id, parser_command_help memory, contract_manifest, config_schema_repositories, app_import_budget, artifact_directory_audit, partial_launch_cleanup, force_reuse x2, axe_run_started_at home-mode cleanup, plus agent_header_panel ImportError collection error

[2026-10-01T09:36:34Z · sase-1dq.8--1] auto default flipped in config/schema/code/tests; 7 flip-caused test failures fixed by pinning explicit chain mode (138 tests in affected files pass, ruff clean); docs consolidated; remaining check failures reproduce identically on clean base and are recorded as PROPOSED FOLLOW-UP

## Dependencies

- **Depends on:** [sase-1dq.7](sase-1dq.7.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1dq.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.8.md) | [sase-1dq.8](sase-1dq.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0abe894`](https://github.com/sase-org/sase/commit/0abe8941403e1c230e4bee2df19b22e22f2b399a) | feat(ace): complete bead sase-1dq.8 next-word and prompt completion work | [sase-1dq.8](sase-1dq.8.md) | 2026-10-01 06:00:14 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1dq.8--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1dq.8.md

<!-- sase:referenced-by:end -->

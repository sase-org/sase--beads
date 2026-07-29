# Bead: sase-av.4 — Recognize and expand artifact references at launch

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.4` · **Size:** medium
**Created:** 2026-07-29 16:48:01 UTC · **Closed:** 2026-07-29 18:23:37 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

prompt-grammar: recognize `@<kind>:<payload>` references in launched prompts through the core scanner and expand them per kind — documents, chats, and artifact files to real paths, commits and bugs to their locators — before file-reference processing, failing the launch clearly when a known-kind reference does not resolve.

## Notes

[2026-07-29T18:23:37Z · sase-av.4] Implemented launch-time artifact-reference expansion/validation before file refs, including path fragments, commit checkout/full-SHA and bug URL locators, literal-zone immunity, clear known-kind failures, and history-safe verbatim recording. Verified 80 focused tests, an end-to-end plans-sidecar resolution smoke check, git diff --check, Symvision, and full just check.

[2026-07-29T18:24:33Z · sase-av.4] Verified 80 focused tests, production plans-sidecar artifact resolution, git diff --check, and full just check.

## Dependencies

- **Depends on:** [sase-av.2](sase-av.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-av.4/README.md) | [sase-av.4](sase-av.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`46b40c5`](https://github.com/sase-org/sase/commit/46b40c5f6610b2ccd97d0e315b853a6563b2ab1a) | feat(artifacts): expand references during prompt launch | [sase-av.4](sase-av.4.md) | 2026-07-29 18:25:21 |

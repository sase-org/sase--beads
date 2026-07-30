# Bead: sase-av.6 — Artifact-reference completion in the prompt bar

[Bead Pages](../README.md) / [sase-av](README.md) / sase-av.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-av.6` · **Size:** large
**Created:** 2026-07-29 16:48:22 UTC · **Closed:** 2026-07-29 19:06:17 UTC
**Plan:** [202607/artifact\_refs\_and\_prompt\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_refs_and_prompt_bar.md)

## Description

prompt-complete: complete artifact references in the prompt bar — kinds after `@`, payloads per kind from warm cached providers for documents, artifact files, chats, commits, and bugs — through a pre-tokenizer context detector, and record used references into file-reference history.

## Notes

[2026-07-29T19:06:17Z · sase-av.6] Implemented two-stage ACE @kind:payload completion with warm project-scoped document/file/chat catalogs, mounted commit/bug snapshots, auto/manual interaction, panel metadata, history/config/help/docs coverage, bounded/no-I/O performance guards, and regression tests. Verified with just install, focused pytest suites (including 143- and 27-test runs), just _lint-symvision, and full just check.

[2026-07-29T19:07:08Z · sase-av.6] Implemented artifact-reference prompt completion; verified full just check including formatting, Ruff, mypy, Symvision, repository validation, tests, coverage, and visual snapshots.

## Dependencies

- **Depends on:** [sase-av.2](sase-av.2.md) ✓
- **Depends on:** [sase-av.5](sase-av.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-av.6--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.6.md#member-code) | [sase-av.6](sase-av.6.md) | 1 |
| [bbugyi200.athena.sase-av.6--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-av.6.md#member-plan) | [sase-av.6](sase-av.6.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e55aab9`](https://github.com/sase-org/sase/commit/e55aab9c92f73f5f902fa58ee39641da6a78686a) | feat(ace): add artifact reference prompt completion | [sase-av.6](sase-av.6.md) | 2026-07-29 19:07:54 |

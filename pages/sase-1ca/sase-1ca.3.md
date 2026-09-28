# Bead: sase-1ca.3 — sase-core append-only archive for every permanent stash removal

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.3` · **Size:** medium
**Created:** 2026-09-28 17:30:12 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

core-stash-archive: in the linked sase-core repo, archive (fsynced, fail-closed, same lock) every popped, purged, evicted, and overwritten stash row before rewriting the stash; add read_prompt_stash_archive and recover_prompt_stash_archive bindings; fsync appends; tests.

## Dependencies

- **Blocks:** [sase-1ca.6](sase-1ca.6.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.3/README.md) | [sase-1ca.3](sase-1ca.3.md) | 0 |

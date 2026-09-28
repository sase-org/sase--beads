# Bead: sase-1ca.3 — sase-core append-only archive for every permanent stash removal

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.3` · **Size:** medium
**Created:** 2026-09-28 17:30:12 EDT · **Closed:** 2026-09-28 17:52:01 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

core-stash-archive: in the linked sase-core repo, archive (fsynced, fail-closed, same lock) every popped, purged, evicted, and overwritten stash row before rewriting the stash; add read_prompt_stash_archive and recover_prompt_stash_archive bindings; fsync appends; tests.

## Notes

[2026-09-28T21:52:01Z · sase-1ca.3] core-stash-archive done in linked sase-core: append-only prompt_stash_archive.jsonl (fsynced, fail-closed, same lock) for pop/purge/evict/overwrite with reasons, read_prompt_stash_archive + recover_prompt_stash_archive core fns and Python bindings, append fsync; new prompt_stash_archive.rs (13 tests) + binding round-trips; full gate sase tool run check succeeded (run 127468d2)

## Dependencies

- **Blocks:** [sase-1ca.6](sase-1ca.6.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.3/README.md) | [sase-1ca.3](sase-1ca.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@df23cce`](https://github.com/sase-org/sase-core/commit/df23ccee7b5e06e95d760f8d9e20f0ebd802b538) | feat(prompt-stash): append-only archive for every permanent stash removal | [sase-1ca.3](sase-1ca.3.md) | 2026-09-28 17:53:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ca.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.3/README.md

<!-- sase:referenced-by:end -->

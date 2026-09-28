# Bead: sase-1ca.4 — Restore and capture hardening in the TUI

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.4` · **Size:** medium
**Created:** 2026-09-28 17:30:13 EDT · **Closed:** 2026-09-28 17:43:59 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

restore-capture-hardening: restore loads from the pop outcome with fail-closed reads and rollback, background stash-task failures are logged and toasted, failed stash appends put the draft back in the bar, and @/q/Q are unavailable while a prompt owns keys.

## Notes

[2026-09-28T21:43:33Z · sase-1ca.4] PROPOSED FOLLOW-UP: just check flags lint fails on clean base tree too (rule 7: closed flag bead sase-1be still has surviving agent_tabs definition); needs a task bead + owner

[2026-09-28T21:43:59Z · sase-1ca.4] Phase 4 done: restore loads from pop outcome with fail-closed keep-read + rollback re-append, stash tasks log+toast on failure, failed appends restore draft to bar, @/q/Q gated while prompt owns keys; 119 related tests pass, ruff+mypy clean, flags-lint failure pre-existing on base tree

## Dependencies

- **Blocks:** [sase-1ca.5](sase-1ca.5.md) ✓ · ⧖ 2026-09-28
- **Blocks:** [sase-1ca.6](sase-1ca.6.md) ✓ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.4/README.md) | [sase-1ca.4](sase-1ca.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aba5d03`](https://github.com/sase-org/sase/commit/aba5d035c2e35849b455edad569fcdbd695cbac7) | fix(ace): harden prompt stash restore, capture, and availability guards | [sase-1ca.4](sase-1ca.4.md) | 2026-09-28 17:46:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ca.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ca.4/README.md

<!-- sase:referenced-by:end -->

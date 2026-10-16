# Bead: sase-1lj.4 — The TUI opens the instruction bundle an agent received

[Bead Pages](../README.md) / [sase-1lj](README.md) / sase-1lj.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10r](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10r.md) · **Assignee:** `sase-1lj.4` · **Size:** medium
**Created:** 2026-10-16 15:15:58 EDT · **Closed:** 2026-10-16 16:28:50 EDT
**Plan:** [202610/e4\_readable\_agents\_md.md](https://github.com/sase-org/sase--plans/blob/main/202610/e4_readable_agents_md.md)

## Description

launch-row: add a public launch-bundle locator, point the Memory lane's as-launched row at the recorded root bundle for explicit runs while old and native runs keep the AGENTS.md snapshot, and (decision files_deck) list bundles in the Files deck with help-text commands.

## Notes

[2026-10-16T20:28:33Z · sase-1lj.4] PROPOSED FOLLOW-UP: sase tool run check fails at SASE validation init memory --check with the same 7 chezmoi home files (sase.md, README.md, AGENTS/CLAUDE/GEMINI/QWEN/OPENCODE.md.tmpl, +9/−11) on this dirty tree and on a clean stash of master; this phase did not edit memory notes. Closed sase-n0 / sase-i7 historically owned the durable generator/shim reconciliation; no open bead currently matches.

[2026-10-16T20:28:50Z · sase-1lj.4] Launch-row shipped: public launch_root_bundle locator; MEMORY lane shows Instructions as launched · NN-<provider> with channel/size/bytes-match-or-MISMATCH for explicit runs and keeps AGENTS.md snapshot for native/fallback/pre-E3; Files deck lists root then helper bundles (DONE dispatch uses instruction_bundle_files; running agents fill a worker cache); help lists sase instructions commands; history.md documents the row. Verified unit tests (114 launch-row/file/help plus import-budget 3519 with _instruction_bundles deferred off first paint), TZ=UTC visual --check for four new goldens, just fix, sase bead epic-symbols (none). sase tool run check 9578f5438fc2594803e25592c6fc4296 failed only at init memory --check; same 7 chezmoi files on clean master (PROPOSED FOLLOW-UP, cites closed sase-n0/sase-i7). Isolated re-runs of the two full-suite flakes passed.

## Dependencies

- **Blocks:** [sase-1lj.5](sase-1lj.5.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lj.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.4/README.md) | [sase-1lj.4](sase-1lj.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`552b38f`](https://github.com/sase-org/sase/commit/552b38f7ed078ace50c73e1ca44fe40d4ebd9f51) | feat(tui): open the launched instruction bundle from MEMORY and Files | [sase-1lj.4](sase-1lj.4.md) | 2026-10-16 16:30:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lj.4][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lj.4/README.md

<!-- sase:referenced-by:end -->

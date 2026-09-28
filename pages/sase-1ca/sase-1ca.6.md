# Bead: sase-1ca.6 — Stash-archive recovery surface (CLI, TUI hints, docs) and core pin

[Bead Pages](../README.md) / [sase-1ca](README.md) / sase-1ca.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tt.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tt.w0.md) · **Assignee:** `sase-1ca.6` · **Size:** medium
**Created:** 2026-09-28 17:30:16 EDT · **Closed:** 2026-09-28 18:59:46 EDT
**Plan:** [202609/never\_lose\_stashed\_prompts.md](https://github.com/sase-org/sase--plans/blob/main/202609/never_lose_stashed_prompts.md)

## Description

stash-archive-recovery: bump the sase-core pin, add guarded archive facade functions, the sase prompt stash-archive list/restore/show CLI, archive hints in purge/evict/delete toasts, docs, and tests.

## Notes

[2026-09-28T22:59:46Z · sase-1ca.6--1] Phase scope delivered (core pin bump, archive facade/CLI/hints/docs/tests). Verified: sase tool run check verdict no_new_failures — all lint gates pass incl. test-waits and symvision; 4839 scoped tests passed; only 2 failures, triaged KNOWN (test_agent_session_terminology) and FLAKY (test_parser_command_help) in unrelated files. Fixed 3 missing sase-test-wait pragmas (pre-existing on base), privatized 3 in-file-only archive sub-handlers, deleted dead prompt_stash_archive_path helper. No epic-symbol entries remain.

## Dependencies

- **Depends on:** [sase-1ca.2](sase-1ca.2.md) ✓ · ⧖ 2026-09-28
- **Depends on:** [sase-1ca.3](sase-1ca.3.md) ✓ · ⧖ 2026-09-28
- **Depends on:** [sase-1ca.4](sase-1ca.4.md) ✓ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ca.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ca.6.md) | [sase-1ca.6](sase-1ca.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f4764b`](https://github.com/sase-org/sase/commit/4f4764b42de68472daae86e4b8d421f422a14021) | feat(prompt-stash): recoverable stash archive with CLI, TUI hints, and docs | [sase-1ca.6](sase-1ca.6.md) | 2026-09-28 19:01:22 EDT |

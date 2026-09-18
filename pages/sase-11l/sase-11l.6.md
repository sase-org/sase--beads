# Bead: sase-11l.6 — Completion and LSP for %hold

[Bead Pages](../README.md) / [sase-11l](README.md) / sase-11l.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ls](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ls.md) · **Assignee:** `sase-11l.6` · **Size:** medium
**Created:** 2026-09-15 22:46:03 EDT · **Closed:** 2026-09-18 07:50:49 EDT
**Plan:** [202609/hold\_directive.md](https://github.com/sase-org/sase--plans/blob/main/202609/hold_directive.md)

## Description

hold-completion-lsp: complete %hold everywhere — new Hood value role, hood candidate rows, WAITING/QUEUED-first agent ranking, proc rows included, ACE wait-clause generalization, and xprompt LSP parity.

## Notes

[2026-09-18T11:37:20Z · sase-11l.6] PROPOSED FOLLOW-UP: usage-probes temp leak guard mismatch — full-suite just check passed tests but failed because an empty /home/bryan/.cache/sase/tmp/usage-probes bucket appeared under the unsandboxed managed temp root during usage-probe tests

[2026-09-18T11:50:49Z · sase-11l.6] Implemented %hold completion/LSP parity; verified cargo tests for core hold/hood and LSP conversion/server paths, rebuilt local Rust dev artifacts, pytest tests/test_xprompt_directive_completion_parity.py -q, SASE_ALLOW_STALE_CORE=1 just check, and sase bead epic-symbols sase-11l.6 reported no --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-11l.10](sase-11l.10.md) ◐ · ⧖ 2026-09-15
- **Depends on:** [sase-11l.5](sase-11l.5.md) ✓ · ⧖ 2026-09-15
- **Blocks:** [sase-11l.9](sase-11l.9.md) ◐ · ⧖ 2026-09-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11l.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11l.6/README.md) | [sase-11l.6](sase-11l.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f852cdc`](https://github.com/sase-org/sase/commit/f852cdcbba7a5901c386ec12bd8190d621a9f3cf) | feat(ace): complete hold directive completions | [sase-11l.6](sase-11l.6.md) | 2026-09-18 07:52:28 EDT |

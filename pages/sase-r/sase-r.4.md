# Bead: sase-r.4 — Wire sase bead work to claim + launch

[Bead Pages](../README.md) / [sase-r](README.md) / sase-r.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 21:21:11 UTC · **Closed:** 2026-04-25 22:07:30 UTC
**Plan:** [202604/epic\_work\_automation.md](https://github.com/sase-org/sase--plans/blob/main/202604/epic_work_automation.md)

## Description

Extend the sase bead work handler from Phase 1: after flipping the flag, build the plan, pre-claim each phase bead, render the multi-prompt, and call launch_agent_from_cwd(query). Add --dry-run and --yes flags. Confirmation prompt (skippable with -y) summarising waves and agent count. On launch failure, attempt to roll back the bead claims and the is_ready_to_work flip; print a clear remediation message either way. Integration test that monkeypatches launch_agent_from_cwd. Glossary entry in memory/short/glossary.md for Epic work automation.

## Dependencies

- **Depends on:** [sase-r.1](sase-r.1.md) ✓
- **Depends on:** [sase-r.2](sase-r.2.md) ✓
- **Depends on:** [sase-r.3](sase-r.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7258025`](https://github.com/sase-org/sase/commit/7258025c43cef2607e8e817bc6b80513eb093816) | feat: wire \`sase bead work\` to pre-claim phases + launch agents (sase-r.4) | [sase-r.4](sase-r.4.md) | 2026-04-25 22:08:18 |

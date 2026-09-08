# Bead: sase-y5.8 — Expose cached usage and explicit refresh in the CLI

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.8` · **Size:** medium
**Created:** 2026-09-07 16:09:25 EDT · **Closed:** 2026-09-08 12:56:52 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

usage-cli: Add sase usage list and refresh, a stable JSON contract, plain/Rich presentation, provider filters, precise exit behavior, completion/help, and offline doctor diagnostics. Build the shared presentation helpers for ACE.

## Notes

[2026-09-08T16:56:52Z · sase-y5.8] Implemented cached usage list/refresh CLI, provider completion, shared usage presentation helpers, offline llm.usage doctor diagnostics, and robust isolated usage-probe cleanup; verified just install, just fmt, just sync-completion-spec, focused usage/completion/doctor/probe tests, CLI smokes, symvision, just check, and no remaining sase-y5.8 epic-symbol entries.

## Dependencies

- **Depends on:** [sase-y5.7](sase-y5.7.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y5.9](sase-y5.9.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.8/README.md) | [sase-y5.8](sase-y5.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3f9c7b4`](https://github.com/sase-org/sase/commit/3f9c7b451655ec5bb6857b7c0b6bfefffdeac49d) | feat(usage): add cached usage CLI | [sase-y5.8](sase-y5.8.md) | 2026-09-08 13:52:40 EDT |

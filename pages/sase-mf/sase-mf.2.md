# Bead: sase-mf.2 — Replace legacy role aliases with the compact config contract

[Bead Pages](../README.md) / [sase-mf](README.md) / sase-mf.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02n.md) · **Assignee:** `sase-mf.2` · **Size:** medium
**Created:** 2026-08-15 14:30:06 EDT · **Closed:** 2026-08-15 16:37:26 EDT
**Plan:** [202608/simplify\_models.md](https://github.com/sase-org/sase--plans/blob/main/202608/simplify_models.md)

## Description

alias_config_contract: reduce built-ins to five direct size aliases, add the three model config fields, migrate runtime routing and state, and diagnose retired names.

## Notes

[2026-08-15T20:09:27Z · sase-mf.2] PROPOSED FOLLOW-UP: Update protected SASE size memory documentation for the compact direct size aliases — sase/memory/sase_sizes.md still describes retired @<size>_worker aliases, but this phase cannot edit memory files without explicit user approval.

[2026-08-15T20:27:54Z · sase-mf.2] PROPOSED FOLLOW-UP: Land or confirm the paired sase-core v0.27.7 release before merging this Python phase — just check now sees size_model_route/select_epic_land_model in published v0.27.7, so this phase will raise the Python sase-core-rs floor to that release.

[2026-08-15T20:37:26Z · sase-mf.2] Implemented compact direct model alias contract and scalar launch model settings; verified with just fmt, targeted pytest suites, git diff --check, and SASE_CORE_DIR=/tmp/sase-core-not-present just check (full-suite escalation passed against published sase-core-rs 0.27.7).

[2026-08-15T20:38:45Z · sase-mf.2] Verified just fmt, git diff --check, targeted pytest suites, and SASE_CORE_DIR=/tmp/sase-core-not-present just check passed with full-suite escalation.

## Dependencies

- **Depends on:** [sase-mf.1](sase-mf.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mf.3](sase-mf.3.md) ◐ · ⧖ 2026-08-15
- **Blocks:** [sase-mf.4](sase-mf.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.2/README.md) | [sase-mf.2](sase-mf.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2fcca46`](https://github.com/sase-org/sase/commit/2fcca46eb36ff1bc23bcc4984f8b1bc09b4f3e1a) | feat!: replace role model aliases with size launch settings | [sase-mf.2](sase-mf.2.md) | 2026-08-15 16:40:39 EDT |

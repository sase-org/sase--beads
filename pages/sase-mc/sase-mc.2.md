# Bead: sase-mc.2 — Make every model-selection path honor disabled providers

[Bead Pages](../README.md) / [sase-mc](README.md) / sase-mc.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02f.md) · **Assignee:** `sase-mc.2` · **Size:** medium
**Created:** 2026-08-15 11:12:03 EDT · **Closed:** 2026-08-15 13:26:59 EDT
**Plan:** [202608/temporary\_provider\_disabling.md](https://github.com/sase-org/sase--plans/blob/main/202608/temporary_provider_disabling.md)

## Description

routing-semantics: introduce one routing-availability seam and apply it to alias pools, ordered fallbacks, temporary alias overrides, default autodetection, provider dispatch, model pickers, and completion catalogs. Preserve direct-selection diagnostics, selector cursor invariants, and automatic restoration on expiry.

## Notes

[2026-08-15T17:26:59Z · sase-mc.2] Verified just install with sase-core-rs 0.27.5, focused provider/invoke pytest (86 passed), earlier model-picker/completion pytest groups (88 and 31 passed), and just check passed with full-suite escalation.

[2026-08-15T17:28:15Z · sase-mc.2] Verified provider-disable routing, model picker/completion filtering, dependency floor ratchet, and full repo gate: just install and just check passed; focused provider/invoke, TUI picker, and completion tests passed.

## Dependencies

- **Depends on:** [sase-mc.1](sase-mc.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mc.3](sase-mc.3.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mc.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.2/README.md) | [sase-mc.2](sase-mc.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`58b9b44`](https://github.com/sase-org/sase/commit/58b9b447fed9d5bc4d7d637fbf428aea43b0f9f0) | feat(llm-provider): honor disabled providers in model routing | [sase-mc.2](sase-mc.2.md) | 2026-08-15 13:29:59 EDT |

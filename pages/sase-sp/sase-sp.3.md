# Bead: sase-sp.3 — Adjudicate deferrals at submit time instead of after the turn

[Bead Pages](../README.md) / [sase-sp](README.md) / sase-sp.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ca](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ca.md) · **Assignee:** `sase-sp.3` · **Size:** medium
**Created:** 2026-08-24 09:19:09 EDT · **Closed:** 2026-08-24 12:09:32 EDT
**Plan:** [202608/finalizer\_commit\_authoring.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_commit_authoring.md)

## Description

adjudicate: replace the free-text `refuse` action with typed `defer` decisions and make `sase final submit` reject unfounded deferrals as repairable validation errors while the agent still holds its context.

## Notes

[2026-08-24T15:45:24Z · sase-sp.3] PROPOSED FOLLOW-UP: Repair home memory initialization drift — just check fails in SASE validation because init memory --check reports unreferenced ~/.local/share/chezmoi/home/sase/memory/obsidian.md plus generated home memory/provider-shim drift.

[2026-08-24T16:09:32Z · sase-sp.3] Implemented submit-time typed deferral validation/adjudication. Verified: just install; just fmt; focused finalizer/recovery/live/refusal tests; core validator; validate-committed-plans; just check passes through fmt/ruff/mypy/feature-flag/pyscripts/test-waits/changelog/patch-terminology/symvision/toobig. just check is blocked only by pre-existing home memory init drift, recorded as PROPOSED FOLLOW-UP; test-scoped escalates to the full suite, previous finalizer failures were fixed and targeted reruns pass; rerun reached 99% with no failures printed but pytest parent stuck and was terminated.

## Dependencies

- **Depends on:** [sase-sp.2](sase-sp.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sp.4](sase-sp.4.md) ◐ · ⧖ 2026-08-24
- **Blocks:** [sase-sp.5](sase-sp.5.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sp.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sp.3/README.md) | [sase-sp.3](sase-sp.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`524d8f2`](https://github.com/sase-org/sase/commit/524d8f26f2b3ff619132248135ef2322349463c5) | feat(finalizers): adjudicate typed deferrals at submit time | [sase-sp.3](sase-sp.3.md) | 2026-08-24 12:12:14 EDT |

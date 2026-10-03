# Bead: sase-1eq.3.1.4 — Terminology guard

[Bead Pages](../README.md) / [sase-1eq.3.1](sase-1eq.3.1.md) / sase-1eq.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.3.md) · **Assignee:** `sase-1eq.3.1.4` · **Size:** small
**Created:** 2026-10-02 19:30:30 EDT · **Closed:** 2026-10-03 04:40:48 EDT
**Plan:** [202610/sase\_modules\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_modules_rename.md)

## Description

guard: Add the contract test that fails on non-TUI xprompt identifiers and paths, allowlisting the legacy homes and the shim.

## Notes

[2026-10-03T08:40:32Z · sase-1eq.3.1.4] PROPOSED FOLLOW-UP: check-scoped failure test_dev_extension_exposes_every_collected_name (missing plan_publication_payload_batches) reproduces on clean base; unrelated to macro guard

[2026-10-03T08:40:48Z · sase-1eq.3.1.4] Added tests/test_macro_terminology.py (contract): path/NAME/import xprompt checks pass; fixed xprompt.name straggler; sase tool run check 830 passed, 1 pre-existing base failure noted as follow-up

## Dependencies

- **Depends on:** [sase-1eq.3.1.3](sase-1eq.3.1.3.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.3.1.4/README.md) | [sase-1eq.3.1.4](sase-1eq.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8de1add`](https://github.com/sase-org/sase/commit/8de1add72ccc730866a078bd9f6d7fd3c0dbd227) | test(sase-modules): add macro terminology guard contract test (sase-1eq.3.1.4) | [sase-1eq.3.1.4](sase-1eq.3.1.4.md) | 2026-10-03 04:42:04 EDT |

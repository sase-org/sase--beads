# Bead: sase-h7.5 — Fail closed at creation for unanswerable gates

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.5` · **Size:** medium
**Created:** 2026-08-07 17:07:50 EDT · **Closed:** 2026-08-07 19:22:15 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

custom-validation: add the missing `kind_validation/custom.py`, reject at creation any option whose effective input schema cannot accept what a client can produce, pin the JSON Schema dialect, and make an omitted `input_schema` mean "no input" instead of the permissive empty schema.

## Notes

[2026-08-07T23:22:15Z · sase-h7.5] Implemented custom-validation: new kind_validation/custom.py validates a client-producible sample against each option's input_schema at creation (unanswerable_option naming the offending required property); omitted input_schema now means NO_INPUT_SCHEMA; JSON Schema dialect pinned to Draft 2020-12 and stamped on stored option/operation schemas; declared input defaults validated against their compiled fragment; submission-time width/depth bounds shared from model_validation and applied at creation; format documented as annotation-only. Verified: just check lint gates all green (fmt, ruff, mypy, keep-sorted, pyscripts, changelog, symvision, toobig, SASE validation, committed plans) and just test-scoped 5456 passed.

## Dependencies

- **Blocks:** [sase-h7.12](sase-h7.12.md) ◐ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.3](sase-h7.3.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.5/README.md) | [sase-h7.5](sase-h7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ff0b765`](https://github.com/sase-org/sase/commit/ff0b765a4d395ef91f9b89aeabd5d3e7d831aed1) | feat(notification-gates)!: fail closed at creation for unanswerable gates | [sase-h7.5](sase-h7.5.md) | 2026-08-07 19:24:06 EDT |

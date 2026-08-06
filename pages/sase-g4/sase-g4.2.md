# Bead: sase-g4.2 — Report an invalid header block from \`sase plan links validate\`

[Bead Pages](../README.md) / [sase-g4](README.md) / sase-g4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ty](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ty/README.md) · **Assignee:** `sase-g4.2` · **Size:** small
**Created:** 2026-08-06 09:05:39 EDT · **Closed:** 2026-08-06 09:25:39 EDT
**Plan:** [202608/plan\_header\_validation.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_header_validation.md)

## Description

links-parity: `_link_validation.py` silently skips a plan whose header disposition is INVALID while `plan_links_refresh` reports `header-invalid` for the same document; give the validator the same issue so the two commands agree on what a broken header block is.

## Notes

[2026-08-06T13:25:39Z · sase-g4.2] Added header-invalid issue emission in _link_validation.py for INVALID plan-header disposition (matching plan_links_refresh.py's code/message convention), added test_validate_reports_invalid_header_block pinning it plus the parser's reason; verified canonical-plan-reports-nothing is already covered by existing tests (test_validate_accepts_plan_without_prompt_bullet, test_validate_passing_run_prints_no_repair_hint). Ran full tests/main/test_plan_links_validate_handler.py (13 passed) and just check (fmt/lint/mypy/symvision/toobig/SASE validation/committed plans/scoped tests all green).

## Dependencies

- **Blocks:** [sase-g4.5](sase-g4.5.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-g4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-g4.2/README.md) | [sase-g4.2](sase-g4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fa8fc69`](https://github.com/sase-org/sase/commit/fa8fc69e46c49bc3367ea274584d7fa928aa1dc9) | fix(sdd): report header-invalid from plan links validate | [sase-g4.2](sase-g4.2.md) | 2026-08-06 09:27:10 EDT |

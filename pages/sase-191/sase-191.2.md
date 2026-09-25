# Bead: sase-191.2 — Show continued stage failures as failures

[Bead Pages](../README.md) / [sase-191](README.md) / sase-191.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rz](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rz.md) · **Assignee:** `sase-191.2` · **Size:** small
**Created:** 2026-09-25 07:43:31 EDT · **Closed:** 2026-09-25 08:29:37 EDT
**Plan:** [202609/e3\_precision\_gate.md](https://github.com/sase-org/sase--plans/blob/main/202609/e3_precision_gate.md)

## Description

continued-stage-output: make tools/run_silent print the failure marker and the captured output for a stage it continues past, instead of a check mark and no output, and pin that with a keep-going test.

## Notes

[2026-09-25T12:29:37Z · sase-191.2] run_silent now prints ✗ + captured output for continued stages (exit 0), never ✓; keep-going test extended; tool tests and sase tool run check pass; noted on sase-18j

## Dependencies

- **Blocks:** [sase-191.3](sase-191.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-191.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.2/README.md) | [sase-191.2](sase-191.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`245dcb5`](https://github.com/sase-org/sase/commit/245dcb55362fca45a0ae4a03d982a059ab38854d) | fix(tools): show continued run\_silent stage failures as failures (sase-191.2) | [sase-191.2](sase-191.2.md) | 2026-09-25 08:31:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-191.2][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-191.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-191.land/README.md

<!-- sase:referenced-by:end -->

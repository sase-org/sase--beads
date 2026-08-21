# Bead: sase-rr.5.2 — Normalize provider identity and dispatch

[Bead Pages](../README.md) / [sase-rr.5](sase-rr.5.md) / sase-rr.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rr.land--2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rr.land.md) · **Assignee:** `sase-rr.5.2` · **Size:** small
**Created:** 2026-08-21 20:27:13 UTC · **Closed:** 2026-08-21 21:06:32 UTC
**Plan:** [202608/finalizer\_integrity\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/finalizer_integrity_closeout.md)

## Description

provider-contract: canonicalize Python distribution identities across discovery and execution and replace exception-based callable-versus-factory detection with an explicit, single-invocation provider contract.

## Notes

[2026-08-21T21:06:06Z · sase-rr.5.2] PROPOSED FOLLOW-UP: flake tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift — failed once under xdist full-suite just check asserting a retired SKILL.md path in rendered inventory output; serial rerun on the same tree passed; unrelated to finalizer provider identity

[2026-08-21T21:06:32Z · sase-rr.5.2] Canonicalized PEP 503 provider refs across discovery, config, required-plugin comparison, dedup, and isolated worker lookup; replaced TypeError factory heuristic with inspect-before-invoke dispatch (method-bearing, zero-arg factory, request callable). Verified mixed-case/punctuation metadata fixtures from discovery through worker execution, single-invocation call counts, and unchanged TypeError identity. just check lint passed; scoped run escalated to full suite (10274 passed) with one unrelated skills-inventory flake recorded as proposed follow-up.

## Dependencies

- **Blocks:** [sase-rr.5.3](sase-rr.5.3.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rr.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rr.5.2/README.md) | [sase-rr.5.2](sase-rr.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3d66071`](https://github.com/sase-org/sase/commit/3d66071d37ce85b736bbf9561f1be0a3dd872478) | fix(finalizers): canonicalize provider identity and dispatch | [sase-rr.5.2](sase-rr.5.2.md) | 2026-08-21 21:07:40 UTC |

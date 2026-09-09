# Bead: sase-yh.5.1 — Bind automatic checkpoint recovery to authenticated durable evidence

[Bead Pages](../README.md) / [sase-yh.5](sase-yh.5.md) / sase-yh.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yh.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yh.land.md) · **Assignee:** `sase-yh.5.1` · **Size:** medium
**Created:** 2026-09-09 07:14:14 EDT · **Closed:** 2026-09-09 08:18:38 EDT
**Plan:** [202609/stitch\_recovery\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/stitch_recovery_landing_repairs.md)

## Description

checkpoint-proof: compare checkpoint run, agent, repository, and complete accepted payload identity through the Rust-backed recovery decision; prove legacy ownership instead of asserting it, surface checkpoint and marker persistence failures, and cover foreign-run, same-subject/different-payload, malformed, and retry cases.

## Notes

[2026-09-09T12:18:00Z · sase-yh.5.1] PROPOSED FOLLOW-UP: Teach linked sase-core scripts/check.sh to export the resolved Python LIBDIR on LD_LIBRARY_PATH before cargo test; a plain just check can fail PyO3 test binaries with missing libpython3.14.so.1.0 when uv Python is selected.

[2026-09-09T12:18:38Z · sase-yh.5.1] Implemented schema-2 Rust-backed pending checkpoint recovery checks with run/agent/operation/full-payload identity matching, Python request wiring, and durable checkpoint/marker failure surfacing. Verified cargo fmt; cargo test -p sase_core pending_commit_checkpoint; cargo test -p sase_core_py pending_commit_checkpoint_bindings_round_trip_json_shapes; focused pytest pending/finalizer/workflow/marker suites (49 passed); just fmt; just check in sase; linked sase-core just check with PYO3_PYTHON and LD_LIBRARY_PATH exported.

## Dependencies

- **Blocks:** [sase-yh.5.3](sase-yh.5.3.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yh.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yh.5.1/README.md) | [sase-yh.5.1](sase-yh.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`27bbd2f`](https://github.com/sase-org/sase/commit/27bbd2f4e4bcab9c364b175ad44c3fa24e13250d) | fix(commit): authenticate checkpoint recovery evidence | [sase-yh.5.1](sase-yh.5.1.md) | 2026-09-09 08:20:06 EDT |

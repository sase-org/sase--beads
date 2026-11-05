# Bead: sase-1qz.6.1.4.1.3 — Submit and resume the pinned recovery request

[Bead Pages](../README.md) / [sase-1qz.6.1.4.1](sase-1qz.6.1.4.1.md) / sase-1qz.6.1.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1qz.6.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.6.1.4.md) · **Assignee:** `sase-1qz.6.1.4.1.3` · **Size:** medium
**Created:** 2026-11-05 10:12:40 EST · **Closed:** 2026-11-05 13:05:50 EST
**Plan:** [202611/recovery\_transaction\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202611/recovery_transaction_completion.md)

## Description

durable_admission: connect the winning reservation to durable typed admission and a reconstructible strict-workspace dispatcher, including cancellation and retry evidence.

## Notes

[2026-11-05T18:01:02Z · sase-1qz.6.1.4.1.3] PROPOSED FOLLOW-UP: Remove the stale sase-1rd symvision entries for write_snapshot and encode_run_prune_review — the gate reports both already properly used, reproducible on the committed base; implementation is tracked by sase-1rd.2 and cleanup belongs with the sase-1rd land agent.

[2026-11-05T18:05:50Z · sase-1qz.6.1.4.1.3] Durable typed recovery admission now persists and binds one request id and Rust dispatch fingerprint before CAS dispatch, reconstructs the strict pinned workspace/name/model dispatcher in a fresh coordinator, exposes request status/resume/cancel helpers, and keeps uncertain dispatch cancellation nonterminal. Verified 186 focused hijack/admission tests, configured formatting and Ruff, and targeted mypy.  reached symvision and failed only on the unrelated stale sase-1rd symbols; that failure reproduces on committed base and is recorded as a proposed follow-up. Epic-symbol audit for this bead was clear.

## Dependencies

- **Depends on:** [sase-1qz.6.1.4.1.2](sase-1qz.6.1.4.1.2.md) ✓ · ⧖ 2026-11-05
- **Blocks:** [sase-1qz.6.1.4.1.5](sase-1qz.6.1.4.1.5.md) ✓ · ⧖ 2026-11-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.6.1.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md) | [sase-1qz.6.1.4.1.3](sase-1qz.6.1.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7896ea6`](https://github.com/sase-org/sase/commit/7896ea657b8ef77c72f16cb309ca70f100e05381) | feat(agent-recovery): persist pinned recovery admission | [sase-1qz.6.1.4.1.3](sase-1qz.6.1.4.1.3.md) | 2026-11-05 14:21:08 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1qz.6.1.4.1.3][1] | Check state after baseline-failing close preflight | 4 |
| read-by | [agent:sase-1qz.6.1.4.1.6][2] | Need sibling phase evidence for integration | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qz.6.1.4.1.6/README.md

<!-- sase:referenced-by:end -->

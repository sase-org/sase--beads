# Bead: sase-1q5.1 — Batch the stranded-work session query per project

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.1` · **Size:** small
**Created:** 2026-10-30 18:38:09 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

stranded-batch: replace the per-assignee index query loop with one batched, chunked query per project, keeping the exact recheck and dedupe, with parity tests and a before/after timing.

## Notes

[2026-10-30T23:19:44Z · sase-1q5.1] stranded-batch timing gh_sase-org__sase: before wall=157.1s queries=238 (per-assignee loop, stashed new code); after wall=4.7s queries=3 (batched, chunk=100). Bead count identical (238). Machine was loaded (concurrent check lane) so treat absolutes as noisy; the query-count drop 238->3 is the structural win.

## Dependencies

- **Blocks:** [sase-1q5.4](sase-1q5.4.md) ◐ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1q5.1.md) | [sase-1q5.1](sase-1q5.1.md) | 0 |

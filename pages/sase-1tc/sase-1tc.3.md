# Bead: sase-1tc.3 — A scheduler stop never silently drops a chop's launch batch (sase-1c2)

[Bead Pages](../README.md) / [sase-1tc](README.md) / sase-1tc.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1dg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1dg.md) · **Assignee:** `sase-1tc.3` · **Size:** large
**Created:** 2026-11-17 11:19:26 EST
**Plan:** [202611/backlog\_epic\_cmdsub\_retries\_launches.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_cmdsub_retries_launches.md)

## Description

chop_launch: journal in-flight chop launch batches and resume them idempotently after a scheduler or service-host stop, with visible notices.

## Notes

[2026-11-18T00:13:46Z · sase-1tc.3] Planning evidence: inspected sase 07aedfc8ca and linked sase-core c5e60d78; phase had no prior work notes and no epic-symbol entries. Existing ordinary clan launch records batch results only after the multi-prompt call returns. Side-effect-free injected SystemExit(143) after 2/4 simulated spawns yielded zero batch progress callbacks; no real agents or runtime state were changed. Typed admission already has durable unit journals but needs original-bundle linkage and startup recovery. Authored and twice validated a five-phase sequential child epic (journal, ordinary_launch, typed_launch, recovery, acceptance), parent_bead=sase-1tc.3, including explicit clan-generation cancellation and a disposable subprocess stop/resume demonstration. Submitting through sase plan propose; implementation and closure remain for approved child work and its land agent.

## Dependencies

- **Depends on:** [sase-1tc.2](sase-1tc.2.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.4](sase-1tc.4.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) | [sase-1tc.3](sase-1tc.3.md) | 0 |

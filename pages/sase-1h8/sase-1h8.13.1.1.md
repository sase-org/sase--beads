# Bead: sase-1h8.13.1.1 — Direct write-through publication without a second sweep or full snapshot

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.1` · **Size:** medium
**Created:** 2026-10-08 14:46:04 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:c6e84b9abb0aa9ec8460fdf0 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

publish-direct: capture the epic-start note/update baseline; fix the stale bead_read_parity expectation so check reaches every crate; add a snapshot-free read-model publication API with writer-captured signatures and a content-generation CAS against the admission witness; route create/note/update publication through it; fix the forced-freshness token shortcut; prove one sweep, zero snapshot loads and token-only next reads.

## Notes

[2026-10-08T18:56:05Z · sase-1h8.13.1.1] Epic-start baseline (before any publish-direct source change): 1x note p50 205.8ms/p95 238.6ms/max 318.9ms, update p50 224.3ms/p95 267.6ms/max 268.3ms (6899 beads/44775 events/2000 streams/91.9% closed); 8x note p50 1205.5ms/p95 1337.9ms/max 1419.4ms, update p50 1186.2ms/p95 1586.2ms/max 1589.1ms (55516 beads/361682 events/16000 streams/92.4% closed). 20 runs, default seed 20261006, artifact file:explicit:c6e84b9abb0aa9ec8460fdf0. Binary built from linked-core 1ff43605 via SASE_ALLOW_STALE_CORE=1 just rust-install (JSON core_revision field echoes the pin cd73d968). Host load avg ~17-24 during run.

## Dependencies

- **Blocks:** [sase-1h8.13.1.2](sase-1h8.13.1.2.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.1/README.md) | [sase-1h8.13.1.1](sase-1h8.13.1.1.md) | 0 |

# Bead: sase-1h8.13.1.1 — Direct write-through publication without a second sweep or full snapshot

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.1` · **Size:** medium
**Created:** 2026-10-08 14:46:04 EDT · **Closed:** 2026-10-08 16:31:09 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:c6e84b9abb0aa9ec8460fdf0 | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

publish-direct: capture the epic-start note/update baseline; fix the stale bead_read_parity expectation so check reaches every crate; add a snapshot-free read-model publication API with writer-captured signatures and a content-generation CAS against the admission witness; route create/note/update publication through it; fix the forced-freshness token shortcut; prove one sweep, zero snapshot loads and token-only next reads.

## Notes

[2026-10-08T18:56:05Z · sase-1h8.13.1.1] Epic-start baseline (before any publish-direct source change): 1x note p50 205.8ms/p95 238.6ms/max 318.9ms, update p50 224.3ms/p95 267.6ms/max 268.3ms (6899 beads/44775 events/2000 streams/91.9% closed); 8x note p50 1205.5ms/p95 1337.9ms/max 1419.4ms, update p50 1186.2ms/p95 1586.2ms/max 1589.1ms (55516 beads/361682 events/16000 streams/92.4% closed). 20 runs, default seed 20261006, artifact file:explicit:c6e84b9abb0aa9ec8460fdf0. Binary built from linked-core 1ff43605 via SASE_ALLOW_STALE_CORE=1 just rust-install (JSON core_revision field echoes the pin cd73d968). Host load avg ~17-24 during run.

[2026-10-08T20:30:46Z · sase-1h8.13.1.1] publish-direct landed in linked sase-core (uncommitted): new read_model/publish.rs with CacheWitness (generation+content_generation+frontier+token), publish_mutation_write (direct one-txn commit, no second sweep, no snapshot load, reducer-truth corrections from resumed upserts), and synchronous guarded repair for gate failures; jsonl writer sibling returns writer-captured signatures; create/note/update routed through it with shared apply_corrections (indexed private copies deleted); ensure_fresh_forced/ensure_fresh Stale arms refresh off the taken sweep (forced path can no longer take the token-only shortcut); backfill_meta_keys gated behind a probe SELECT; io_stats adds full_sweeps/snapshot_loads/sig_rows_written/published_rows; new tests/publish_direct.rs (7 tests). DESIGN DELTA: backdated/config/stream-set gate failures take the synchronous repair (fresh sweep + tail-or-rebuild, readiness-only) instead of Invalidated+drop, because the plan also requires bead_read_model_parity to pass unchanged and that harness accounts exactly one monotonic refresh per changed store (drop+cold-rebuild resets outcome counters and overflows its accounting); Invalidated is reserved for commit write faults and unusable repair inputs. Baseline artifact file:explicit:c6e84b9abb0aa9ec8460fdf0.

[2026-10-08T20:30:58Z · sase-1h8.13.1.1] sase-1h8 DISCOVERED ISSUE #3 is fixed: bead_read_parity event_store_supports_read_queries_without_legacy_projection now asserts the issues.jsonl-missing warning is ABSENT for event stores, and new test doctor_still_warns_when_a_legacy_store_lacks_issues_jsonl asserts it still appears for legacy stores. sase-1h8 land agent can skip it. editor directive-matrix contract passes (32 directive tests green).

[2026-10-08T20:31:09Z · sase-1h8.13.1.1] Verified: epic-start baseline captured (1x note p95 238.6ms, update p95 267.6ms; 8x note p95 1337.9ms, update p95 1586.2ms; artifact file:explicit:c6e84b9abb0aa9ec8460fdf0). New publish_direct suite (7 tests) proves one admission sweep, zero snapshot loads/replays, one sig row per changed stream, token-only next reads, cache==replay, CAS skip without stale pairing, fault fail-open with exactly one durable event, in-place edit caught at admission, and synchronous repair with exactly one rebuild on backdate. bead_read_parity (16), bead_read_model_parity (6), bead lib suite (504 bead tests), directive matrix all green. sase tool run check in sase-core: exit 0 (fmt, features, clippy -D warnings, all tests, script tests). No epic-symbols. Work is uncommitted in the linked sase-core checkout for host finalizers.

## Dependencies

- **Blocks:** [sase-1h8.13.1.2](sase-1h8.13.1.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.1/README.md) | [sase-1h8.13.1.1](sase-1h8.13.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@6460581`](https://github.com/sase-org/sase-core/commit/646058197f5ced5231ed478b8a716678007f0156) | feat(beads): direct write-through read-model publication without second sweep or snapshot | [sase-1h8.13.1.1](sase-1h8.13.1.1.md) | 2026-10-08 16:44:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h8.13.1.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.1/README.md

<!-- sase:referenced-by:end -->

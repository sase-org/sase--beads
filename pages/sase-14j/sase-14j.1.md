# Bead: sase-14j.1 — Reduce bead event streams into an actor-keyed touch index in sase-core

[Bead Pages](../README.md) / [sase-14j](README.md) / sase-14j.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oa.md) · **Assignee:** `sase-14j.1` · **Size:** medium
**Created:** 2026-09-20 16:31:05 EDT · **Closed:** 2026-09-20 17:18:21 EDT
**Plan:** [202609/agent\_bead\_touches.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_bead_touches.md)

## Description

core-index: add the actor/bead touch reduction over beads/events/streams, its versioned index wire, incremental signature-cached refresh, and the read-only touch query, exposed through PyO3 bindings with fixture and parity tests.

## Notes

[2026-09-20T21:16:44Z · sase-14j.1] PROPOSED FOLLOW-UP: sase bead touched -a/--all (sase-14j.3) cannot include the store-owner actor — the core index drops email and validate_agent_name-rejected actors at reduction time per the plan identity rules; either drop the flag or add an index opt-in before writing the parser

[2026-09-20T21:17:12Z · sase-14j.1] PROPOSED FOLLOW-UP: touch-index status can lag for beads reopened by task_plus_one_recorded (the reopen decision depends on close/observation timestamps the reduction does not replay); fine for display, revisit if the panel keys behavior off status

[2026-09-20T21:17:41Z · sase-14j.1] HANDOFF for sase-14j.2..: core API in sase-core crates/sase_core/src/bead/touch_index.rs, PyO3 names bead_touch_index_wire_schema_version / bead_touch_index_refresh(beads_dir, index_path) / bead_touch_index_query(index_path, actors=None) / bead_touch_index_status(beads_dir, index_path). Rows carry an extra stream_id field (cache bookkeeping, ignore it). actors=None returns every actor so the facade can apply the globalize_owned_agent_name legacy-bare match itself. Refresh locks <index_path>.lock itself (env SASE_BEAD_TOUCH_INDEX_LOCK_TIMEOUT, default 2s), skips the write when nothing changed, and reports reduced_streams for the exactly-the-streams-it-wrote test. Release timings on the live store (1590 streams): cold refresh 165ms, warm 22ms, query 17ms (parses the whole 2.4MB index each call), so the Python loader must keep its mtime cache. sase-core needs a release containing these bindings before the sase Python side can call them

[2026-09-20T21:18:21Z · sase-14j.1] Added crates/sase_core/src/bead/touch_index.rs in sase-core: pure reduce_stream_touches, incremental signature-cached refresh_bead_touch_index (locked, atomic, skips write when unchanged), read-only query_bead_touches, stat-only bead_touch_index_status, versioned wire (schema 1), PyO3 bindings + binding-list docs. Verified: 26 inline tests (verb table, excluded/unknown ops, malformed lines, owner/email dropping, mixed globalized/bare actors, title overwrite, verb counts, first/last bounds, cache hit via sentinel, changed/new/vanished streams, schema bump rebuild, corrupt index cache miss, lock timeout), fixture parity test pinning the full snapshot, PyO3 binding test of complete returned dicts; sase-core just check exit 0 (fmt, clippy -D warnings, workspace tests incl. sase_core_py). Smoke on the live store (1590 streams, release): cold 165ms, warm 22ms, query 17ms. No sase-repo files changed; no epic-symbols.

## Dependencies

- **Blocks:** [sase-14j.2](sase-14j.2.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14j.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14j.1/README.md) | [sase-14j.1](sase-14j.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@9a5c568`](https://github.com/sase-org/sase-core/commit/9a5c56809a66261d194de07c4a7f400a10706328) | feat(bead): reduce event streams into an actor-keyed touch index | [sase-14j.1](sase-14j.1.md) | 2026-09-20 17:19:43 EDT |

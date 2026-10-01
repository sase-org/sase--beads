# Bead: sase-1dr.4 — Memory history semantics, cache, and query bindings in sase-core

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.4` · **Size:** large
**Created:** 2026-09-30 19:09:22 EDT · **Closed:** 2026-09-30 23:58:52 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

memory-history-core: build the semantic layer over file_history. This covers subjects (note, web, strand, instructions, asset), per-version shim aliasing by blob equality, version classes and summaries, commit-footer provenance, cause attribution for instruction renders, changesets and the feed, sparkline volumes, the persisted per-scope snapshot, and the GIL-releasing query bindings. It is tested against a fixture corpus modelled on real SASE history.

## Notes

[2026-10-01T04:03:04Z · sase-1dr.4.1.land] Child epic sase-1dr.4.1 completed this phase. The phase description (parent plan section 9, memory-history-core) is present in sase-core at 11f29c3: subject identity and shim aliasing, version classes and summaries, commit provenance, instruction causes, changesets and the feed, the per-scope snapshot, upstream_ahead, and the eight GIL-releasing memory_history_ bindings, tested on the fixture corpus. just test -p sase_core memory_history passed 36 tests and just test -p sase_core_py memory_history passed 2. The epic close recorded resolution done and this phase closed with it as delegated work landed. The containing epic sase-1dr is left to its land agent. Python history service remains sase-1dr.5.

## Dependencies

- **Depends on:** [sase-1dr.2](sase-1dr.2.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.3](sase-1dr.3.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.5](sase-1dr.5.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.4.md) | [sase-1dr.4](sase-1dr.4.md) | 0 |

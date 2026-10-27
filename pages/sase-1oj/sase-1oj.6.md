# Bead: sase-1oj.6 — Measure the write reduction on athena

[Bead Pages](../README.md) / [sase-1oj](README.md) / sase-1oj.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.ae](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ae.md) · **Assignee:** `sase-1oj.6` · **Size:** small
**Created:** 2026-10-26 16:07:29 EDT · **Closed:** 2026-10-27 12:52:21 EDT
**Plan:** [202610/athena\_disk\_write\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_disk_write_diet.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:1e18c3d5d24ecf9a40c1fe61 | attached via sase artifact create --bead |
| related | file:explicit:83534cbe39e78e4b85571979 | attached via sase artifact create --bead |
| related | file:explicit:b06d16eb7cd09c143f556ce0 | attached via sase artifact create --bead |
| related | file:explicit:b6d0a76cc01204986040cafe | attached via sase artifact create --bead |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

verify-athena: once the host runs the landed code (propose the reinstall through a gate if not), re-measure each source and athena's daily root-NVMe writes against the baseline, record the results, and file follow-ups for any missed target.

## Notes

[2026-10-27T16:51:23Z · sase-1oj.6] Athena measurement complete 2026-10-27 12:27–12:44 EDT. Host was current (no reinstall). Report file:explicit:1e18c3d5d24ecf9a40c1fe61. Scan cache 423 KB/99 records (was 104 MB/15428); Codex live sqlite 0.27–0.41 MB (was 347 MB); read-model 0.43.0 serving with 0 rebuilds/20s and 0 WAL unlink; daily nvme1n1 4.09 TB/24h misses 1.4–2.5 TB because the window includes overnight crate ping-pong plus workspace rust/test IO.

[2026-10-27T16:51:30Z · sase-1oj.6] PROPOSED FOLLOW-UP: Daily nvme1n1 writes still 4.09 TB/24h vs 1.4–2.5 TB baseline — last 24 h includes pre-restart crate-version ping-pong (epic note #7) plus post-restart workspace cargo/pytest/sccache; host-level SASE_TMPDIR on /mnt/hades and swap-off-root already listed as not-in-epic.

[2026-10-27T16:51:38Z · sase-1oj.6] PROPOSED FOLLOW-UP: Durable per-version bead read-model isolation (epic note #7) — mixed crate_version fleets rewrite one shared cache; 0.43.0 is stable after the 08:54 restart but 39 processes already map a (deleted) .so from the 12:23 rebuild and the next core bump will ping-pong again.

[2026-10-27T16:51:46Z · sase-1oj.6] PROPOSED FOLLOW-UP: Codex orphan sweep leaves 6 dead 2026-07-19 shadow homes under ~/.cache/sase/codex_home because rescue-on-collision refuses delete when a stray rollout path already exists in ~/.codex/sessions (~0.8 MB leftover; 87 dirs/1.1 GB otherwise gone).

[2026-10-27T16:51:54Z · sase-1oj.6] PROPOSED FOLLOW-UP: athena has no `codex` on PATH so sase-1oj.6 could not repeat `codex exec --json`; live shadow state_5.sqlite is 278–426 KB matching sase-1oj.5, but there is no on-host session_meta timing.

[2026-10-27T16:52:21Z · sase-1oj.6] Athena re-measure 2026-10-27 12:27–12:44 EDT; host already on 691ef46153 / core 0.43.0 so no reinstall. Scan cache 423 KB/99 records (was 104 MB/15428); Codex live sqlite 0.27–0.41 MB (was 347 MB); read-model 0.43.0 serving with 0 rebuilds and 0 WAL unlink in 20 s; test-binary bytes cited from sase-1oj.3. Daily nvme1n1 4.09 TB/24h misses 1.4–2.5 TB (overnight crate ping-pong + workspace rust/test IO). Report file:explicit:1e18c3d5d24ecf9a40c1fe61. Follow-ups noted on this bead. epic-symbols none.

## Dependencies

- **Depends on:** [sase-1oj.3](sase-1oj.3.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oj.4](sase-1oj.4.md) ✓ · ⧖ 2026-10-26
- **Depends on:** [sase-1oj.5](sase-1oj.5.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1oj.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1oj.6/README.md) | [sase-1oj.6](sase-1oj.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:ak--3][1] | Corroborate pre-existing ACE failures and inspect assigned unstick bead | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.ak.md

<!-- sase:referenced-by:end -->

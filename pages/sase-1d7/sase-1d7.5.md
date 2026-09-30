# Bead: sase-1d7.5 — Sequence-fenced pending-ack overlay and monotonic snapshot cache

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.5` · **Size:** medium
**Created:** 2026-09-30 07:18:12 EDT · **Closed:** 2026-09-30 11:09:58 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

pending-ack-fence: stamp snapshot reads with a read sequence, keep in-flight acks as a pending overlay every reconcile path honors, reject stale snapshots in the cache, narrow failure restore to owned identities, and stop re-confirmations from invalidating undo.

## Notes

[2026-09-30T15:09:14Z · sase-1d7.5--1] PROPOSED FOLLOW-UP: just check _setup fails identically on clean base tree — validate_sase_core_rs prompt-prediction probe expects confident=True/ghost=[the] but installed sase_core_rs 0.36.1 returns confident=False/ghost=[]; sase-core checkout fast-forwarded to origin/master e890bb8 ahead of pyproject window >=0.35.0,<0.36.0 (same skew sase-1d7.4 recorded and closed on)

[2026-09-30T15:09:36Z · sase-1d7.5--1] PROPOSED FOLLOW-UP: symvision still flags pre-existing get_roster_generation in _roster_generation.py (committed by sase-1d7.4, untouched by this phase); left alone because downstream phases sase-1d7.6/.8/.12 are in flight and may consume it

[2026-09-30T15:09:58Z · sase-1d7.5--1] pending-ack fence done: 6 fence tests + 128 unread/notification TUI tests pass; ruff, fmt, mypy clean; symvision clean for this phase's symbols (renamed get_notif_read_seq private); just check _setup Rust prompt-prediction probe fails identically on clean base tree (pre-existing sase-core skew, recorded as follow-up citing sase-1d7.4)

## Dependencies

- **Blocks:** [sase-1d7.12](sase-1d7.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.8](sase-1d7.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.5.md) | [sase-1d7.5](sase-1d7.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`63c7eb5`](https://github.com/sase-org/sase/commit/63c7eb57e2aef04349519c39e8d5db37a7468a02) | feat(agents): sequence-fenced pending-ack overlay and monotonic snapshot cache | [sase-1d7.5](sase-1d7.5.md) | 2026-09-30 11:12:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.5--1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.5.md

<!-- sase:referenced-by:end -->

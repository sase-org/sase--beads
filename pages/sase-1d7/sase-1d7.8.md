# Bead: sase-1d7.8 — Read-free ack completion and a coalescing ack writer

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.8` · **Size:** medium
**Created:** 2026-09-30 07:18:17 EDT · **Closed:** 2026-09-30 13:31:47 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

ack-pipeline: delete the synchronous post-ack store read, apply ack outcomes to the cached snapshot by id, schedule only the guarded async resync, and drain queued acks through one coalescing worker that issues one Rust call per batch.

## Notes

[2026-09-30T17:31:22Z · sase-1d7.8--1] PROPOSED FOLLOW-UP: just check _setup fails on clean base too — tools/validate_sase_core_rs prompt-prediction probe expects confident=True/ghost=[the] but installed sase-core-rs 0.36.1 wheel returns confident=False/ghost=[] (byte-identical output on stashed base, exit 1); validator-vs-core skew independent of this phase

[2026-09-30T17:31:47Z · sase-1d7.8--1] ack-pipeline done: coalescing ack writer (one Rust call per batch), read-free completion by cached-snapshot id set, guarded async resync only. Verified: 100 passed across test_unread_ack_pipeline + 9 neighboring unread/ack suites; ruff + mypy clean on touched files; symvision output byte-identical to clean base (5 pre-existing items only, my 3 new ones fixed by privatizing file-local helpers); just-check _setup validator failure reproduces identically on clean base, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-1d7.12](sase-1d7.12.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.5](sase-1d7.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.7](sase-1d7.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.9](sase-1d7.9.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.8.md) | [sase-1d7.8](sase-1d7.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f57024d`](https://github.com/sase-org/sase/commit/f57024dbdc98e0c481e6eabda3d01e217e21d314) | feat(agents): unread ack pipeline with coalescing writer and cached-snapshot completion | [sase-1d7.8](sase-1d7.8.md) | 2026-09-30 13:35:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.8--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.8.md

<!-- sase:referenced-by:end -->

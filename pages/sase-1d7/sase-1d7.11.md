# Bead: sase-1d7.11 — Cheap fleet reprojection signature computed before projection

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.11` · **Size:** medium
**Created:** 2026-09-30 07:18:21 EDT · **Closed:** 2026-09-30 11:47:18 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

fleet-signature-cheap: replace the recursive deep-freeze projection signature with a structural signature from the roster generation and fleet wire revisions, checked before project_clan_tree runs, with host-level freshness fields patched in the header only.

## Notes

[2026-09-30T14:42:30Z · sase-1d7.11] Implemented fleet-signature-cheap: structural pre-projection signature (roster generation + removal generation + per-row wire keys/revisions/status/clan/attention/followed/dispatch + snapshot identities on FleetRowsProjection) checked before project_clan_tree; skip path patches volatile host fields onto live rows + header. Removed _freeze_projection_value/_agents_projection_signature. Inline-verified: standalone probe 21/21, ruff format+check clean, mypy clean on src (test-file mypy Liskov error pre-exists on clean tree, outside src gate). Remaining: cold rust build (extension missing here) + repo tests + idle bench + epic-symbols + close.

[2026-09-30T15:46:55Z · sase-1d7.11--2] PROPOSED FOLLOW-UP: just test/just check _setup blocked by pre-existing validate_sase_core_rs prompt-prediction probe failure (expects confident=True ghost=[the], installed sase_core_rs 0.36.1 from sase-core master returns confident=False ghost=[]); reproduces identically on clean base tree with this diff stashed, so unrelated to fleet-signature-cheap; needs sase-core/sase checkout contract resync

[2026-09-30T15:47:18Z · sase-1d7.11--2] fleet-signature-cheap done and verified. Targeted tests 34/34 pass (fleet_refresh_laziness, roster_generation, catalog_pages, projection) via direct pytest; ruff check+format clean; mypy clean on 3 changed src files; epic-symbols empty. Idle bench after: fleet_refresh unchanged p50/p95/max 0.049/0.061/0.38ms (before 80.78/104.09/124.12ms, now near header-cost as designed), forced 18.07/21.35/229.09ms (before 97.94/159.75/166.89ms; max is host-contention spike). just test/just check _setup blocked by pre-existing validate_sase_core_rs prompt-prediction skew that fails identically on clean base tree; recorded as PROPOSED FOLLOW-UP, not a blocker per phase instructions.

## Dependencies

- **Depends on:** [sase-1d7.3](sase-1d7.3.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1d7.4](sase-1d7.4.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.11.md) | [sase-1d7.11](sase-1d7.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2fade65`](https://github.com/sase-org/sase/commit/2fade653babb1adf2deeb637c6b66cec392c4786) | feat(agents): cheap fleet reprojection signature checked before projection | [sase-1d7.11](sase-1d7.11.md) | 2026-09-30 11:49:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d7.11--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d7.11.md

<!-- sase:referenced-by:end -->

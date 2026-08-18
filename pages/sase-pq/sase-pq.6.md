# Bead: sase-pq.6 — A pending gate refreshes when its type presentation changes

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.6` · **Size:** small
**Created:** 2026-08-18 09:38:06 EDT · **Closed:** 2026-08-18 12:09:55 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

refresh: fold the frozen display block into the reconciler's presentation fingerprint and bump the presentation format version so pending gates carrying the old, typeless presentation are replaced.

## Notes

[2026-08-18T16:09:30Z · sase-pq.6] PROPOSED FOLLOW-UP: just check is red on unused public monitor_row_is_settled — src/sase/ace/tui/models/agent_family_members.py exports it and uses it only in-file (landed in 845253505); make it private or give it a non-test consumer. Unrelated to this refresh phase.

[2026-08-18T16:09:55Z · sase-pq.6] Verified: presentation_fingerprint now hashes the resolved task_type_display block (not the raw slug) via the chop's already-loaded registry; untyped fingerprints omit the key. Format version bumped 3→4. Glyph change replaces a pending typed gate; untyped beads do not churn across registry changes; version-3 fingerprints are replaced on the next tick. 2765 scoped tests passed.

[2026-08-18T16:10:45Z · sase-pq.6] Verified: presentation_fingerprint now hashes the resolved task_type_display block (not the raw slug) via the chop's already-loaded registry; untyped fingerprints omit the key. Format version bumped 3→4. Glyph change replaces a pending typed gate; untyped beads do not churn across registry changes; version-3 fingerprints are replaced on the next tick. 2765 scoped tests passed.

## Dependencies

- **Depends on:** [sase-pq.5](sase-pq.5.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.7](sase-pq.7.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.6/README.md) | [sase-pq.6](sase-pq.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b87c0b1`](https://github.com/sase-org/sase/commit/b87c0b176777fc72912e0aea5142e2eee3ba22fa) | feat(bead): refresh pending gates when type presentation changes | [sase-pq.6](sase-pq.6.md) | 2026-08-18 12:11:33 EDT |

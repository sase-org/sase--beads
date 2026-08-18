# Bead: sase-pq.1 — A gate may declare one subject chip

[Bead Pages](../README.md) / [sase-pq](README.md) / sase-pq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.060](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.060.md) · **Assignee:** `sase-pq.1` · **Size:** medium
**Created:** 2026-08-18 09:38:04 EDT · **Closed:** 2026-08-18 10:12:02 EDT
**Plan:** [202608/task\_type\_gate\_presentation.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_type_gate_presentation.md)

## Description

chip: add the generic `presentation.chip` field (glyph, label, optional color), normalize and protect it like `panel_icon`, project it into notification `action_data`, and add the tolerant zero-I/O reader every render surface uses.

## Notes

[2026-08-18T14:12:02Z · sase-pq.1] Verified presentation.chip: normalize_gate_chip accepts glyph+label and optional #RRGGBB color and rejects malformed objects with invalid_presentation on presentation.chip; create_gate projects gate_chip_glyph/label and writes gate_chip_color only when a color is present; forging those keys via presentation.action_data is reserved_action_data; gate_chip_from_action_data returns a usable chip or None for the tolerance table (junk in every position) without raising. just check passed (scoped escalated to the full suite because the Justfile gained the sase-pq.3 epic-symbol for the reader).

[2026-08-18T14:13:09Z · sase-pq.1] Verified presentation.chip: normalize_gate_chip accepts glyph+label and optional #RRGGBB color and rejects malformed objects with invalid_presentation on presentation.chip; create_gate projects gate_chip_glyph/label and writes gate_chip_color only when a color is present; forging those keys via presentation.action_data is reserved_action_data; gate_chip_from_action_data returns a usable chip or None for the tolerance table (junk in every position) without raising. just check passed (scoped escalated to the full suite because the Justfile gained the sase-pq.3 epic-symbol for the reader).

## Dependencies

- **Blocks:** [sase-pq.2](sase-pq.2.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.3](sase-pq.3.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.4](sase-pq.4.md) ✓ · ⧖ 2026-08-18
- **Blocks:** [sase-pq.5](sase-pq.5.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-pq.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-pq.1/README.md) | [sase-pq.1](sase-pq.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4cca5f2`](https://github.com/sase-org/sase/commit/4cca5f2ce0e2fe43bf4bd192ef3d8d2f9d230a3d) | feat(notification\_gates): add generic presentation.chip subject field | [sase-pq.1](sase-pq.1.md) | 2026-08-18 10:14:00 EDT |

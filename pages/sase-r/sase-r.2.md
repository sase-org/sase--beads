# Bead: sase-r.2 — XPromptTag expansion + new built-in bd/work\_phase\_bead + tag-based lookup

[Bead Pages](../README.md) / [sase-r](README.md) / sase-r.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-04-25 21:20:58 UTC · **Closed:** 2026-04-25 21:50:11 UTC
**Plan:** [202604/epic\_work\_automation.md](https://github.com/sase-org/sase--plans/blob/main/202604/epic_work_automation.md)

## Description

Add create_epic_bead, work_phase_bead, land_epic to XPromptTag. Tag bd/new_epic, bd/land_epic in default_config.yml. Add bd/work_phase_bead (parameterised variant of bd/next that takes explicit bead_id), tagged work_phase_bead. Add a small helper in src/sase/bead/work.py (or src/sase/bead/xprompts.py) that resolves the three tags via get_by_tag_strict, raising a clear error if a user has tagged two xprompts with the same tag. Tests: tag enum parses, three built-ins resolvable by tag, user override wins.

## Notes

COMMIT: 5279183d

## Dependencies

- **Blocks:** [sase-r.4](sase-r.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8163af7`](https://github.com/sase-org/sase/commit/8163af7e3d809ec3c7dbc67b51e3c702a6c5a34a) | feat: XPromptTag expansion + bd/work\_phase\_bead built-in + tag-based lookup (sase-r.2) | [sase-r.2](sase-r.2.md) | 2026-04-25 21:50:14 |

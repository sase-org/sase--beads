# Bead: sase-1cu.1 — Shared save-location picker modal and choice model

[Bead Pages](../README.md) / [sase-1cu](README.md) / sase-1cu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u8.md) · **Assignee:** `sase-1cu.1` · **Size:** medium
**Created:** 2026-09-29 18:58:46 EDT · **Closed:** 2026-09-29 20:01:56 EDT
**Plan:** [202609/save\_location\_picker.md](https://github.com/sase-org/sase--plans/blob/main/202609/save_location_picker.md)

## Description

picker: build the pure choice builders (hotkeys, default rules, badges, previews) and the SaveLocationPickerModal with loading and type-ahead support, CSS, docs section, unit tests, and PNG snapshots.

## Notes

[2026-09-29T23:59:56Z · sase-1cu.1] PROPOSED FOLLOW-UP: just check is red on the clean base tree — patch/stitch terminology gate fails on 14 defects in sase-core fixture at_bearing_notes.jsonl and symvision fails on pre-existing private imports (_kitty_graphics_support, _roster_for_issue); none are in files this phase touched

[2026-09-30T00:01:56Z · sase-1cu.1] Picker phase done: save_location_choices builders + SaveLocationPickerModal with loading/type-ahead, CSS, ace.md section, 30 unit/modal tests green, 70 with neighbors, 3 PNG goldens inspected and check-clean, ruff/mypy clean, 4 later-phase symbols whitelisted under sase-1cu; just-check reds are pre-existing base failures recorded as follow-up

## Dependencies

- **Blocks:** [sase-1cu.2](sase-1cu.2.md) ◐ · ⧖ 2026-09-29
- **Blocks:** [sase-1cu.3](sase-1cu.3.md) ◐ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cu.1/README.md) | [sase-1cu.1](sase-1cu.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a4bbd3`](https://github.com/sase-org/sase/commit/1a4bbd3e7633959573b2bf616f7a0fbc23e3b22e) | feat(ace): add save location picker modal and choice builders | [sase-1cu.1](sase-1cu.1.md) | 2026-09-29 20:06:05 EDT |

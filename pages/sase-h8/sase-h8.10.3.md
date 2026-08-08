# Bead: sase-h8.10.3 — Close the wait-idiom gate gaps that let the retired pattern back in

[Bead Pages](../README.md) / [sase-h8.10](sase-h8.10.md) / sase-h8.10.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) · **Assignee:** `sase-h8.10.3` · **Size:** medium
**Created:** 2026-08-08 10:56:33 EDT · **Closed:** 2026-08-08 11:21:19 EDT
**Plan:** [202608/flake\_class\_residue.md](https://github.com/sase-org/sase--plans/blob/main/202608/flake_class_residue.md)

## Description

gate-gaps: widen `tools/check_test_wait_helpers` past the two roots and the one function name it currently matches so it catches the sixth `_wait_until` copy, the inline `for _ in range(N): await pilot.pause()` bounded-wait loops that landed after the epic's waits phase, and the raw ACE panel injections sase-h8.6 asked for; migrate every call site the widened check reports.

## Notes

[2026-08-08T15:21:19Z · sase-h8.10.3] Verified tools/check_test_wait_helpers exits zero after migration; tests/test_check_test_wait_helpers_tool.py passed (8); restricted SASE_CONTENTION_REPEAT=1 just test-contention over migrated files passed 196/196 with 0 failed nodes; final just check passed.

[2026-08-08T15:22:46Z · sase-h8.10.3] Verified tools/check_test_wait_helpers; pytest -q tests/test_check_test_wait_helpers_tool.py passed (8 tests); SASE_CONTENTION_REPEAT=1 just test-contention on migrated files passed (196 tests); just check passed.

## Dependencies

- **Blocks:** [sase-h8.10.4](sase-h8.10.4.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.3/README.md) | [sase-h8.10.3](sase-h8.10.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3c771b7`](https://github.com/sase-org/sase/commit/3c771b77c90d12fc6c8e75c5303afea1c6622d61) | test: retire private bounded wait idioms | [sase-h8.10.3](sase-h8.10.3.md) | 2026-08-08 11:23:46 EDT |

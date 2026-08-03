# Bead: sase-en.2 — Build only the invoked command's subparser

[Bead Pages](../README.md) / [sase-en](README.md) / sase-en.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.2` · **Size:** medium
**Created:** 2026-08-03 12:40:08 UTC · **Closed:** 2026-08-03 13:38:29 UTC
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

parser: give create_parser an opt-in only= hint so a normal sase <cmd> run registers just that command's subparser, drive it from a single shared command registry so the full and narrow paths cannot drift, and stop parser_artifact from importing the heavy artifact facade for one tuple of argparse choices.

## Notes

[2026-08-03T13:37:22Z · sase-en.2] PROPOSED FOLLOW-UP: Repair or intentionally refresh the two Config Center Agent CLI PNG snapshots — test_config_center_agent_clis_marked_png_snapshot and test_config_center_agent_clis_update_preview_png_snapshot reproducibly mismatch their committed goldens in isolation by 0.670357% and 0.281415% changed pixels; inspect the .pytest_cache/sase-visual actual/diff artifacts before accepting any golden update.

[2026-08-03T13:38:29Z · sase-en.2] Verified 26 focused parser/root-entry tests; full and narrow bead-show output is byte-identical for full, compact, and JSON formats; bare/help/full-help/unknown-command fallbacks are byte-identical; all format, Ruff, mypy, Symvision, and validation stages pass; fresh parser import averages 91 ms. Full suite reached 25,735 passes; its contention failure passed in isolation and the two unrelated reproducible PNG mismatches are recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-en.4](sase-en.4.md) ◐
